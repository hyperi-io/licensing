# HyperI Licensing

**Single Source of Truth** for standard licensing, contribution, and security policy files included in every HyperI GitHub repository.

## Files

| File | Purpose |
|------|---------|
| [`LICENSE`](LICENSE) | FSL-1.1-ALv2 license with Australian law notice and AI/ML restriction |
| [`AI-TRAINING-POLICY.md`](AI-TRAINING-POLICY.md) | AI / Machine Learning training restriction policy |
| [`COMMERCIAL.md`](COMMERCIAL.md) | Commercial licensing requirements and corporate group rules |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Contribution guidelines (DCO, Conventional Commits, semantic-release) |
| [`SECURITY.md`](SECURITY.md) | Vulnerability disclosure policy |
| [`robots.txt`](robots.txt) | AI training crawler blocklist (permits standard search indexing) |

## License Summary

HyperI projects are licensed under the **Functional Source License, Version 1.1, ALv2 Future License** (FSL-1.1-ALv2).

- **Permitted**: Internal use, self-hosting, non-commercial education and research
- **Requires commercial licence**: SaaS/PaaS to third parties, OEM embedding, reselling, intra-group hosting
- **AI/ML training**: Not permitted without written consent (see [AI-TRAINING-POLICY.md](AI-TRAINING-POLICY.md))
- **Apache 2.0 conversion**: Each version becomes Apache 2.0 on the second anniversary of its release

See [COMMERCIAL.md](COMMERCIAL.md) for full details on when a commercial licence is required.

## Usage

These files are the canonical source for all HyperI repositories. To set up a new repo:

```bash
# Clone and copy to your new repository
git clone https://github.com/hyperi-io/licensing.git /tmp/licensing
cp /tmp/licensing/LICENSE /tmp/licensing/COMMERCIAL.md \
   /tmp/licensing/CONTRIBUTING.md /tmp/licensing/SECURITY.md \
   /tmp/licensing/AI-TRAINING-POLICY.md /tmp/licensing/robots.txt \
   /path/to/new-repo/
```

### PyPI / Python Packages

For Python packages distributed via PyPI, include the AI training policy
in your package metadata:

```toml
[project]
license = "LicenseRef-FSL-1.1-ALv2-NoAI"
license-files = ["LICENSE", "COMMERCIAL.md", "AI-TRAINING-POLICY.md"]
classifiers = ["License :: Other/Proprietary License"]

[project.urls]
"License" = "https://github.com/hyperi-io/licensing/blob/main/LICENSE"
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

- The `LICENSE` file references the canonical FSL-1.1-ALv2 at [fsl.software](https://fsl.software)
- Release dates for Apache 2.0 conversion are tracked via GitHub releases in each project
- Copyright year should be updated if creating repos in future years
- All files reference HYPERI PTY LIMITED (ABN 31 622 581 748)
- The `robots.txt` is sourced from [ai-robots-txt/ai.robots.txt](https://github.com/ai-robots-txt/ai.robots.txt)

## Contact

- **Commercial licensing**: sales@hyperi.io
- **AI/ML licensing enquiries**: sales@hyperi.io
- **Security reports**: security@hyperi.io
