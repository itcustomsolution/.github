# Contributing to IT Custom Solution engineering surfaces

Thanks for your interest. Most repositories under `itcustomsolution` are private
product and operations code. This guide covers the public organization profile and
any repository that explicitly accepts external contribution.

## Products listed on the organization profile

Public product index (substantiable URLs):

- Winrove: https://winrove.com
- OpsTicket: https://tryopsticket.com
- OnboardIQ: https://tryonboardiq.com
- DeliverOps is retired; see the [current product index](https://itcustomsolution.com/products).

Firm site: https://itcustomsolution.com

## How to propose a change

1. Open an issue on the relevant repository describing the problem and the
   intended change. Do not include customer data, credentials, or bid material.
2. Prefer a focused pull request against `main` with a clear test or verification
   command in the description.
3. Do not add marketing claims that BrandHouse would reject (fabricated past
   performance, banned certification language, SOC 1/2 claims).
4. Secrets never belong in git. Use the approved secret manager path for the
   product.

## What we will not merge

- Changes that bypass send, deploy, payment, or approval chokepoints
- Default-generated empty README replacements that remove substantiable product
  facts from public-facing docs
- Contributions that require unverified customer testimonials or invented metrics

## Security reports

Follow the [security policy](SECURITY.md). Use private vulnerability reporting
where available; keep exploitable details and sensitive data out of public issues.

## License and ownership

Unless a repository states otherwise, code and docs remain owned by
IT Custom Solution LLC.
