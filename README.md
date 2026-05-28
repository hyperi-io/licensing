> DRAFT v0 -- NOT LEGAL ADVICE -- MUST BE REVIEWED BY AUSTRALIAN COUNSEL BEFORE USE.
> This README documents an in-progress migration from FSL-1.1-ALv2 to BUSL-1.1.

# HyperI Licensing

**Single Source of Truth** for standard licensing, contribution, and security policy files included in every HyperI GitHub repository.

## Notice

Licensed under BUSL-1.1 (see [LICENSE](LICENSE)). Additional terms: the
AFFILIATE annexure ([LICENSE-ANNEXURE-AFFILIATE.md](LICENSE-ANNEXURE-AFFILIATE.md)),
the AUSTRALIA annexure ([LICENSE-ANNEXURE-AUSTRALIA.md](LICENSE-ANNEXURE-AUSTRALIA.md)),
and the AI-TRAINING-POLICY ([AI-TRAINING-POLICY.md](AI-TRAINING-POLICY.md)).
Each additional instrument is independently severable: it operates alongside
the LICENSE, is not incorporated into the BUSL-1.1 grant, and a holding that
any one instrument is invalid does not affect the LICENSE, the Additional Use
Grant, or any other instrument.

## Files

| File | Purpose |
|------|---------|
| [`LICENSE`](LICENSE) | Business Source License 1.1 (BUSL-1.1) -- verbatim frame, four parameters, and the Additional Use Grant |
| [`LICENSE-ANNEXURE-AFFILIATE.md`](LICENSE-ANNEXURE-AFFILIATE.md) | Affiliate / corporate-group terms (separable annexure) |
| [`LICENSE-ANNEXURE-AUSTRALIA.md`](LICENSE-ANNEXURE-AUSTRALIA.md) | Australian-law overlay (separable annexure) |
| [`AI-TRAINING-POLICY.md`](AI-TRAINING-POLICY.md) | AI / Machine Learning terms (separate, severable instrument) |
| [`COMMERCIAL.md`](COMMERCIAL.md) | Commercial licensing requirements and corporate group rules |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Contribution guidelines (DCO, Conventional Commits, semantic-release) |
| [`SECURITY.md`](SECURITY.md) | Vulnerability disclosure policy |
| [`robots.txt`](robots.txt) | AI training crawler blocklist (permits standard search indexing) |

## License Summary

HyperI projects are licensed under the **Business Source License 1.1** (SPDX: BUSL-1.1).

- **Default grant**: Copy, modify, create derivative works, redistribute, and non-production use
- **Production use permitted by the Additional Use Grant**, except for providing the software to third parties as a Hosted Service (SaaS / PaaS / managed service)
- **Requires commercial licence**: Hosted/managed service to third parties, OEM embedding, reselling, intra-group hosting
- **AI/ML training**: Not permitted without written consent (separate severable instrument; see [AI-TRAINING-POLICY.md](AI-TRAINING-POLICY.md))
- **Apache 2.0 conversion**: Each version becomes Apache 2.0 on its Change Date (the third anniversary of that version's release; per-version rolling)

See [COMMERCIAL.md](COMMERCIAL.md) for full details on when a commercial licence is required.

## Usage

These files are the canonical source for all HyperI repositories. To set up a new repo:

```bash
# Clone and copy to your new repository
git clone https://github.com/hyperi-io/licensing.git /tmp/licensing
cp /tmp/licensing/LICENSE /tmp/licensing/COMMERCIAL.md \
   /tmp/licensing/LICENSE-ANNEXURE-AFFILIATE.md \
   /tmp/licensing/LICENSE-ANNEXURE-AUSTRALIA.md \
   /tmp/licensing/CONTRIBUTING.md /tmp/licensing/SECURITY.md \
   /tmp/licensing/AI-TRAINING-POLICY.md /tmp/licensing/robots.txt \
   /path/to/new-repo/
```

Each consuming repository must then fill in the per-repo `LICENSE`
parameters (Licensed Work and the per-version Change Date = release date plus
three years) as described in the comment block at the top of `LICENSE`.

### PyPI / Python Packages

For Python packages distributed via PyPI, include the AI training policy
in your package metadata:

```toml
[project]
license = "LicenseRef-BUSL-1.1-HyperI"
license-files = ["LICENSE", "LICENSE-ANNEXURE-AFFILIATE.md", "LICENSE-ANNEXURE-AUSTRALIA.md", "COMMERCIAL.md", "AI-TRAINING-POLICY.md"]
classifiers = ["License :: Other/Proprietary License"]

[project.urls]
"License" = "https://github.com/hyperi-io/licensing/blob/main/LICENSE"
"Affiliate Annexure" = "https://github.com/hyperi-io/licensing/blob/main/LICENSE-ANNEXURE-AFFILIATE.md"
"Australia Annexure" = "https://github.com/hyperi-io/licensing/blob/main/LICENSE-ANNEXURE-AUSTRALIA.md"
"AI Training Policy" = "https://github.com/hyperi-io/licensing/blob/main/AI-TRAINING-POLICY.md"
"Commercial Licensing" = "https://github.com/hyperi-io/licensing/blob/main/COMMERCIAL.md"
```

## Maintenance

All edits to these files should be made in **this repository only**. Do not modify copies in downstream repositories directly.

## GitHub Copilot Settings

HyperI uses **Copilot Business** which is exempt from GitHub's AI training
data collection. The following org-level settings should be configured at
`https://github.com/organizations/hyperi-io/settings/copilot/policies`:

| Setting | Value | Reason |
|---------|-------|--------|
| Suggestions matching public code | **Block** | Avoid inadvertently pulling in copyleft-licensed code |
| Content exclusion | See patterns below | Prevent Copilot from reading sensitive files |

### Recommended Content Exclusion Patterns

Add these at org level (Settings > Copilot > Content exclusion):

```
**/.env*
**/secrets/**
**/*.pem
**/*.key
**/*.p12
**/*.pfx
**/*.jks
**/*.keystore
**/credentials*
**/*secret*
**/*token*
**/vault/**
**/openvpn-profiles/**
**/.aws/**
**/.azure/**
**/.kube/config
**/terraform.tfstate*
**/terraform.tfvars*
**/*.auto.tfvars
```

### Individual Opt-Out

Contributors using Copilot on personal (Free/Pro) plans should opt out
of AI training at: `https://github.com/settings/copilot/features`

Disable: **"Allow GitHub to use my data for AI model training"**

This must be done before **April 24, 2026** when GitHub's new TOS
(Section J) takes effect.

## Notes

- The `LICENSE` file reproduces the canonical Business Source License 1.1 (SPDX: BUSL-1.1) verbatim, with only the four parameters and the Additional Use Grant filled in
- Release dates for the per-version Apache 2.0 conversion (Change Date = release date plus three years) are tracked via GitHub releases in each project
- Copyright year should be updated if creating repos in future years
- All files reference HYPERI PTY LIMITED (ABN 31 622 581 748)
- The `robots.txt` is sourced from [ai-robots-txt/ai.robots.txt](https://github.com/ai-robots-txt/ai.robots.txt)

## Contact

- **Commercial licensing**: sales@hyperi.io
- **AI/ML licensing enquiries**: sales@hyperi.io
- **Security reports**: security@hyperi.io
