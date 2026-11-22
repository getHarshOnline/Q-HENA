# Review rights before release

Q-HENA inherits work through HENA, MUON, Q-MUON, Reckon and MONAD. Before publication, deployment, distribution, packaging or an alternative commercial offer, review the exact inherited files and proposed release together. The [licensing account](../README.md#licence) describes the selected policy, current declarations and pending inherited-rights review.

## Inventory and acceptance

The planned rights-and-notices manifest must identify the frozen HENA source, selected Q-MUON, Reckon and MONAD bases, and the candidate release tree. Trace MUON material inherited through Q-MUON as well. Include the full file inventory and classification, inherited notices, who can grant each right, dependency and generated-file evidence, licence conclusions, corresponding-source arrangements and unresolved exceptions. Keep Reckon's mixed-licence components separate by their actual grants.

Review each proposed act on models and data separately from copyright in the repository. Permission to run a model, retain its outputs, evaluate, train, derive another model or publish data cannot be inferred from a code licence.

Harsh or counsel records acceptance separately from the inventory. Neither document supplies a missing right. Review the additions notice and the README's licence statement against the inventory, including the distinction between implemented code and placeholder files, before accepting them into the release tree.

## Proposed record locations

| Location or type | Purpose |
| --- | --- |
| `contracts/manifests/q-hena-rights-notice.v1.json` | Content-addressed inventory and conclusions for one candidate |
| `contracts/schemas/rights/rights-notice-manifest.v1.schema.json` | Shared manifest schema |
| `contracts/fixtures/rights/` | Required manifest and refusal cases |
| `QHenaRightsAcceptanceV1` | Separate acceptance by Harsh or counsel |

These records and schemas are planned and do not exist yet. RTEPL's selected policy is AGPL-3.0-or-later for material it controls. Establish each inherited component's actual grant and any unresolved exception before offering the release; the selected policy does not replace upstream terms or supply missing rights.
