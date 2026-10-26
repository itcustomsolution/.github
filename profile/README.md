# IT Custom Solution LLC

**Technology services, government-contracting workflows and accountable automation.**

We are a New York technology firm serving government and commercial buyers. Our work spans pursuit and teaming, consulting and AI advisory, managed IT, cloud, security, software and staffing. This GitHub organization is where we publish reusable tools and practical guidance from that work.

[The firm](https://itcustomsolution.com) · [Founder: Olufela “Lu” Fagbure](https://github.com/Lu-ITC) · [Capability statement](https://itcustomsolution.com/capability-statement.pdf)

## Start with the problem you need to solve

| Your task | Public project | What it gives you | Boundary to understand |
| --- | --- | --- | --- |
| Find federal opportunities from an MCP client | [sam-gov-mcp](https://github.com/itcustomsolution/sam-gov-mcp) | Read-only SAM.gov notice search, pagination and notice lookup | Requires your SAM.gov API key; no awards, attachment downloads or bid scoring |
| Review a solicitation's instructions | [bid-deadline-check](https://github.com/itcustomsolution/bid-deadline-check) | Local extraction of deadlines, page limits, forms and requirements from text or PDFs | A review aid: most real documents return **NEEDS REVIEW**; no submission authorization |
| Put a human decision before an agent action | [approval-gate-mcp](https://github.com/itcustomsolution/approval-gate-mcp) | Expiring, single-use approvals bound to the requested action | The executor must enforce the gate; it is not a sandbox against the same OS user |
| Make a task ready for the next person | [task-handoff-check](https://github.com/itcustomsolution/task-handoff-check) | JSON checks for owner, next action, blockers and completion evidence references | Consistency does not establish truth, reference availability or permission to act |
| Check that delivered files still match | [delivery-evidence-check](https://github.com/itcustomsolution/delivery-evidence-check) | SHA-256 manifests and local file-integrity checks | Keep the manifest independently trusted; matching hashes do not prove authenticity or completion |
| Decide how to approach a bid or registration | [govcon-smallbiz-toolkit](https://github.com/itcustomsolution/govcon-smallbiz-toolkit) | Three readable checklists, also packaged as agent skills | General guidance with human review; not legal advice or a compliance assessment |

New to the tools? [Try a local handoff and file-integrity walkthrough](https://github.com/itcustomsolution/.github/blob/main/docs/public-tools-walkthrough.md). It uses synthetic data and needs no account or API key.

## Releases you can inspect

Release and registry snapshot: **26 October 2026**. These are early 0.x tools; review the release notes and each repository's limitations before adoption. A source branch, a GitHub release and a package-registry publication are separate states.

| Project | Published evidence | Runtime / license |
| --- | --- | --- |
| approval-gate-mcp | [GitHub v0.4.0](https://github.com/itcustomsolution/approval-gate-mcp/releases/tag/v0.4.0) · [npm 0.4.0](https://www.npmjs.com/package/@itcustomsolution/approval-gate-mcp/v/0.4.0) | Node.js 22+ · [MIT](https://github.com/itcustomsolution/approval-gate-mcp/blob/master/LICENSE) |
| sam-gov-mcp | [GitHub v0.2.1](https://github.com/itcustomsolution/sam-gov-mcp/releases/tag/v0.2.1) · [npm 0.2.0](https://www.npmjs.com/package/@itcustomsolution/sam-gov-mcp/v/0.2.0); **0.2.1 is not on npm in this snapshot** | Node.js 22+ · [MIT](https://github.com/itcustomsolution/sam-gov-mcp/blob/main/LICENSE) |
| task-handoff-check | [GitHub v0.1.1](https://github.com/itcustomsolution/task-handoff-check/releases/tag/v0.1.1) · [PyPI 0.1.1](https://pypi.org/project/task-handoff-check/0.1.1/) | Python 3.10+ · [MIT](https://github.com/itcustomsolution/task-handoff-check/blob/main/LICENSE) |
| delivery-evidence-check | [GitHub v0.2.0](https://github.com/itcustomsolution/delivery-evidence-check/releases/tag/v0.2.0) · [PyPI 0.2.0](https://pypi.org/project/delivery-evidence-check/0.2.0/) | Python 3.10+ · [MIT](https://github.com/itcustomsolution/delivery-evidence-check/blob/main/LICENSE) |
| bid-deadline-check | [GitHub v0.2.0](https://github.com/itcustomsolution/bid-deadline-check/releases/tag/v0.2.0) · [PyPI 0.2.0](https://pypi.org/project/bid-deadline-check/0.2.0/) | Python 3.10+ · [MIT](https://github.com/itcustomsolution/bid-deadline-check/blob/main/LICENSE) |
| govcon-smallbiz-toolkit | [Source checklists and packaging checks](https://github.com/itcustomsolution/govcon-smallbiz-toolkit); no tagged release at this date | Markdown; Python for packaging checks · [MIT](https://github.com/itcustomsolution/govcon-smallbiz-toolkit/blob/master/LICENSE) |

The Python tools declare 3.10 as their minimum; use a currently maintained Python release for a new environment. The repository READMEs link test evidence and show commands to run the checks yourself. Test results demonstrate the tested scope, not production certification.

## How the work fits together

The tools address separate decisions: find a notice, review its requirements, record a handoff, verify file integrity and enforce an approval at the execution boundary. They can be used independently. They are not an automatically connected procurement platform, and none removes the need for an accountable reviewer.

Our commercial product brands have their own scope and access paths:

| Product | Focus | Where to evaluate it |
| --- | --- | --- |
| Winrove | Government-contracting workflows across pursuit, proposal, contract-team readiness and delivery records | [Product information and scoped evaluation](https://winrove.com) |
| OpsTicket | IT practice, hands-on skills assessment and evidence for recruiting | [Product information and examples](https://tryopsticket.com) |

Both are brands of IT Custom Solution LLC. OnboardIQ and DeliverOps are no longer offered as separate products; their relevant capabilities fold into Winrove. Public tools, illustrative product examples and a product's deployed capabilities have different evidence: consult the product site for current access and availability.

## Work with ITC

For a pursuit, advisory engagement or technology requirement, share the scope, role and decision you need to make. Our [firm website](https://itcustomsolution.com) and [public compliance posture](https://github.com/itcustomsolution/compliance-posture) provide buyer information. Certifications and procurement representations require the applicable current evidence; an open-source release does not establish them.

- **Founder & Director:** Olufela “Lu” Fagbure
- **Founded:** 2021 · **Headquarters:** New York, NY
- **Procurement identifiers:** UEI PR9KWJPM4JU9 · CAGE 91CE1
- **General:** [hello@itcustomsolution.com](mailto:hello@itcustomsolution.com)
- **Sales and teaming:** [sales@itcustomsolution.com](mailto:sales@itcustomsolution.com)
- **Phone:** +1 (646) 671-3399 · [Schedule a conversation](https://cal.com/itcustomsolution)

## Contribute

Start with the relevant repository's setup, tests and contribution guidance. Use small, reproducible examples with synthetic data. See our [contribution guide](https://github.com/itcustomsolution/.github/blob/main/CONTRIBUTING.md) and [security reporting policy](https://github.com/itcustomsolution/.github/blob/main/SECURITY.md). Keep credentials, customer information and private bid material out of public issues and pull requests.
