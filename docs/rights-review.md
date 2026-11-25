# Review rights before release

Q-HENA carries HENA's protocol headers and copies support files or definitions from MONAD and Q-MUON. The kernel pins MONAD, Q-MUON and Reckon. Review the exact files, dependencies and proposed use together before publication, deployment, distribution, packaging or an alternative commercial offer. The [licensing account](../README.md#licence) describes the selected policy and current declarations.

## Inventory and acceptance

The planned rights-and-notices manifest identifies the frozen HENA source, selected Q-MUON, Reckon and MONAD versions, and the candidate release tree. Trace MUON material inherited through Q-MUON as well. Record the full file inventory, inherited notices, who can grant each right, resolved dependencies and generated output, licence conclusions, corresponding-source arrangements and unresolved exceptions. Record Reckon's own licence and the terms for each third-party component or tool the proposed release uses.

Review each proposed act on models and data separately from copyright in the repository. Permission to run a model, retain its outputs, evaluate, train, derive another model or publish data cannot be inferred from a code licence.

Harsh or counsel records acceptance separately from the inventory, based on the evidenced grants and the proposed use. Check the [additions notice](../LICENSE-ADDITIONS.md) and [licence statement](../README.md#licence) against the exact release tree.

## Proposed record locations

| Location or type | Purpose |
| --- | --- |
| `contracts/manifests/q-hena-rights-notice.v1.json` | Content-addressed inventory and conclusions for one candidate |
| `contracts/schemas/rights/rights-notice-manifest.v1.schema.json` | Shared manifest schema |
| `contracts/fixtures/rights/` | Required manifest and refusal cases |
| `QHenaRightsAcceptanceV1` | Separate acceptance by Harsh or counsel |

These records and schemas are planned and do not exist yet. RTEPL's selected policy is AGPL-3.0-or-later for material it controls. Establish each inherited component's actual grant and any unresolved exception before offering the release; the selected policy does not replace upstream terms or supply missing rights.
