# Source provenance and portable releases

WP00.03 follows the [accepted Design profile](https://github.com/ArcForges/ArcForges-Design/blob/5322d698a1b650a52a5a139d986dd85b00b48581/docs/assurance/reference-coverage-and-provenance.md).
ArcSlate owns its current source and release tooling. Dated bootstrap instructions
describe historical initialization; the retired repository is not an implementation
input. The application remains native C# with Avalonia/Skia rendering and published
gRPC-Web clients. The transport protocol does not supply browser UI technology.

## Introduce and review reused material

Complete `eng/provenance/template.json` as a new revisioned record in
`eng/provenance/records` before copying, translating or generating reused material.
Identify the exact repository, commit and paths, file-level licence, attribution,
targets and hashes, disposition, independent verification, full notices and lifetime.
Generated material identifies its generators and inputs. Temporary reuse also names
an owner and observable removal condition.

The Licensing and Provenance Owner reviews those facts against the closed five-row
decision table in `eng/policy/reuse-policy.json`. An authorized maintainer review may
exercise that role; the approval field alone is not evidence. Boundary decisions
belong to Architecture. Record conflicts in `eng/provenance/conflicts`; unresolved
material is not accepted or distributed. Never introduce an implicit exception.

`eng/provenance/files.json` accounts for every tracked and non-ignored new file.
Review must also detect newly imported content inside existing authored files.
Used records are immutable: retain the original, create a superseding revision and
update active bindings. CI uses the event's trusted comparison commit and requires
the corresponding Git history. The source summary is deterministic and preserves
the full upstream licences and existing dependency notices.

## Current implementation and verification

The original WP00.03 audit reconciled root and upstream legal texts against pinned sources.
Its four tooling/test files used the reviewed ArcNotes commit
`e40423a1b14ce8341de35748cc2a093c7c9b77a7`, with recorded product-name substitutions.
The existing ArcSlate tool/test baseline was compared before replacement. Full AGPL
terms and the original adapted checker's Apache attribution and terms remain present.
Builds use this owner's files and exact published dependencies.

Run the commands in [CONTRIBUTING](../CONTRIBUTING.md). The C# repository `check`
validates the inventory, records, source hashes, history and notices. After a reviewed
record change, `provenance-notice` renders the source summary. Tests cover missing
fields/records, forbidden licence boundaries, modified bytes, unsafe paths, removed
history and changed notices.

Native staging requires clean reviewed source. One publication-handoff check
inspects the actual ZIP/tar members and retain full legal texts plus
`notices/source-provenance.txt` and `notices/provenance-source.json`. Missing or changed
notices, wrong or dirty source identity, duplicate/case-colliding names, traversal and
links are rejected even when an archive's outer hash matches its manifest.

Current CI and publication follow the [accepted validation policy](https://github.com/ArcForges/ArcForges-Design/blob/47db6670a727317939b91245e8c0b288834acf99/docs/assurance/ci-and-local-validation-policy.md). Three Windows/Linux candidates and offline/static/security checks replace the five-host runtime matrix. No public asset download or runtime retest is required. These checks do not establish commercial activation.

## WP02.04 successor

`arcnotes-provenance-tools-r2` binds the reviewed ArcNotes support identity implementation at `0c797e30690a10d8798ddca19ca7f37b16cecf01`. It preserves r1, establishes expected transformed hashes before adaptation, and declares ArcSlate-specific future media/storage producers. The active inventory binds all 16 imported source/build/test files. The portable README preserves source attribution and the corresponding-source location alongside the full root licence. Any optional local runtime result identifies its actual tested artifact.

The active r3 successor records owner-authored CI/release reduction against the same ArcNotes origin. It preserves r1/r2, their attribution and all unchanged runtime code. Its revised workflow/tool/test bindings remove mandatory smoke/screenshot inputs and repeated validation while retaining one publication handoff integrity check.
