# A local handoff and file-integrity walkthrough

Two different questions arise when someone says work is ready:

1. Does the handoff name an owner, next step, blockers and evidence consistently?
2. Do the supplied files still match the bytes recorded in a manifest?

`task-handoff-check` answers the first structural question. `delivery-evidence-check` answers the second. Neither validates the truth of a report, grants authority, or performs the work. This is a manual example using two independent tools, not a built-in integration.

## 1. Use an isolated environment

The commands below use a POSIX shell and Python 3.10 or later; prefer a currently maintained Python. Run them in a new working directory. All names, tasks and files here are synthetic.

```sh
mkdir itc-tools-demo
cd itc-tools-demo
python3 -m venv .venv
. .venv/bin/activate
python -m pip install 'task-handoff-check==0.1.1' 'delivery-evidence-check==0.2.0'
```

Installation downloads packages. The checks themselves work locally without network calls. Release evidence: [task-handoff-check v0.1.1](https://github.com/itcustomsolution/task-handoff-check/releases/tag/v0.1.1) and [delivery-evidence-check v0.2.0](https://github.com/itcustomsolution/delivery-evidence-check/releases/tag/v0.2.0). Both are MIT licensed.

## 2. Create a fictional file and a handoff

```sh
mkdir artifacts
printf '%s\n' 'Synthetic review: example only; no real release approved.' > artifacts/review.txt
cat > handoff.json <<'JSON'
{
  "schema_version": 1,
  "objective": "Prepare the fictional review for a second reader",
  "owner": "Sample Maintainer",
  "status": "in_progress",
  "next_action": "Ask a reviewer to read the fictional report",
  "inputs": [{"label": "sample report", "path": "artifacts/review.txt"}],
  "evidence": [],
  "blockers": [],
  "completion_criteria": [{
    "description": "A second reader checks the fictional report",
    "met": false,
    "evidence": []
  }]
}
JSON
task-handoff-check handoff.json --json
```

Expected: exit **0**, `ok: true`, `scope: "handoff_consistency"` and `freshness: "not_evaluated"`. The task is still `in_progress`. The tool does not open the referenced report or contact the owner.

## 3. Record and verify the files

```sh
delivery-evidence-check create --root . handoff.json artifacts/review.txt > manifest.json
delivery-evidence-check verify manifest.json --root . --json
```

Expected: exit **0**, `ok: true`, `scope: "local_file_integrity"`, `files_checked: 2`, and no issues. Shell redirection writes the manifest; the tool does not write files. The manifest is deliberately outside the input list.

This co-located manifest is suitable for a demonstration. For a real exchange, retain a trusted copy separately from the files and the party that can change them. A person able to change both the content and its recorded hash can defeat this comparison.

## 4. Observe a failure

```sh
printf '%s\n' 'Synthetic change after the manifest was created.' >> artifacts/review.txt
delivery-evidence-check verify manifest.json --root . --json
```

Expected: exit **1**, `ok: false` and an issue with code `hash_mismatch`. Treat this as a stop for review; do not regenerate the manifest merely to make the check pass.

To see a different failure, mark the unfinished handoff complete without adding completion evidence:

```sh
python - <<'PY'
import json
from pathlib import Path
handoff = json.loads(Path('handoff.json').read_text())
handoff['status'] = 'complete'
handoff['next_action'] = None
Path('invalid-handoff.json').write_text(json.dumps(handoff))
PY
task-handoff-check invalid-handoff.json --json
```

Expected: exit **1**, `ok: false` and an issue with code `incomplete_criterion`. This checks that the completion claim agrees with the document's own criteria. A convincingly written false claim could still pass the structural checks.

## Where to go next

- [Handoff schema, freshness checks and library API](https://github.com/itcustomsolution/task-handoff-check#handoff-format)
- [Manifest schema, byte budgets and filesystem limits](https://github.com/itcustomsolution/delivery-evidence-check#manifest-format)
- [Human approvals at the execution boundary](https://github.com/itcustomsolution/approval-gate-mcp#trusted-execution-boundary), if the next step has a side effect

Use only files you are permitted to inspect. Keep real customer records, credentials and internal review material out of public reproductions. This walkthrough uses synthetic text so it can be shared without exposing such material.
