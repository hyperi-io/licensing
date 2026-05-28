# HyperI Licensing

**Single Source of Truth** for standard licensing, contribution, and security policy files included in every HyperI GitHub repository.

## Notice

The default public license is BUSL-1.1 (see [LICENSE](LICENSE)). Separate
instruments operate alongside, but are not incorporated into, the BUSL-1.1 grant:
the AFFILIATE annexure ([LICENSE-ANNEXURE-AFFILIATE.md](LICENSE-ANNEXURE-AFFILIATE.md))
and the AI-TRAINING-POLICY ([AI-TRAINING-POLICY.md](AI-TRAINING-POLICY.md)).

The AUSTRALIA annexure ([LICENSE-ANNEXURE-AUSTRALIA.md](LICENSE-ANNEXURE-AUSTRALIA.md))
is a jurisdiction-specific overlay only for recipients to whom Australian law
applies. It is not part of the default public license grant.

## Files

| File | Purpose |
|------|---------|
| [`LICENSE`](LICENSE) | Business Source License 1.1 (BUSL-1.1) -- verbatim frame, HyperI parameters, and the Additional Use Grant |
| [`LICENSE-ANNEXURE-AFFILIATE.md`](LICENSE-ANNEXURE-AFFILIATE.md) | Affiliate / corporate-group terms (separable annexure) |
| [`LICENSE-ANNEXURE-AUSTRALIA.md`](LICENSE-ANNEXURE-AUSTRALIA.md) | Australian-law overlay for recipients to whom Australian law applies |
| [`AI-TRAINING-POLICY.md`](AI-TRAINING-POLICY.md) | AI / Machine Learning terms (separate, severable instrument) |
| [`COMMERCIAL.md`](COMMERCIAL.md) | Commercial licensing requirements and corporate group rules |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Contribution guidelines (DCO, Conventional Commits, semantic-release) |
| [`SECURITY.md`](SECURITY.md) | Vulnerability disclosure policy |
| [`robots.txt`](robots.txt) | AI training crawler blocklist (permits standard search indexing) |

## License Summary

HyperI projects are licensed under the **Business Source License 1.1** (SPDX: BUSL-1.1).

- **Default grant**: Copy, modify, create derivative works, redistribute, and non-production use
- **Production use permitted by the Additional Use Grant**, except for providing the software to third parties outside your corporate group as a Hosted Service (SaaS / PaaS / managed service)
- **Requires commercial licence**: Hosted/managed service to external parties, and shared or centralised intra-group hosting (one entity operating the software as a service for its affiliates)
- **No commercial licence required**: Internal use, internal group use where each entity runs its own instance, self-hosting, and non-hosted redistribution or embedding that complies with the LICENSE
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
   /tmp/licensing/CONTRIBUTING.md /tmp/licensing/SECURITY.md \
   /tmp/licensing/AI-TRAINING-POLICY.md /tmp/licensing/robots.txt \
   /path/to/new-repo/
```

The `LICENSE` is self-contained: the Licensed Work is the software, source code,
documentation, and associated materials in the receiving repository, and each
version converts on the third anniversary of its first public distribution under
BUSL-1.1.

Copy `LICENSE-ANNEXURE-AUSTRALIA.md` only where the repository needs to publish
the Australian-law overlay for recipients to whom Australian law applies.

### PyPI / Python Packages

For Python packages distributed via PyPI, include the AI training policy
in your package metadata:

```toml
[project]
license = "LicenseRef-BUSL-1.1-HyperI"
license-files = ["LICENSE", "LICENSE-ANNEXURE-AFFILIATE.md", "COMMERCIAL.md", "AI-TRAINING-POLICY.md"]
classifiers = ["License :: Other/Proprietary License"]

[project.urls]
"License" = "https://github.com/hyperi-io/licensing/blob/main/LICENSE"
"Affiliate Annexure" = "https://github.com/hyperi-io/licensing/blob/main/LICENSE-ANNEXURE-AFFILIATE.md"
"Australian Law Overlay" = "https://github.com/hyperi-io/licensing/blob/main/LICENSE-ANNEXURE-AUSTRALIA.md"
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

This should be done before contributors use Copilot with HyperI repositories.

## Contact

- **Commercial licensing**: sales@hyperi.io
- **AI/ML licensing enquiries**: sales@hyperi.io
- **Security reports**: security@hyperi.io
