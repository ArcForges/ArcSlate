# WP02.04 support identity

`ArcSlate --build-info --evidence <path.json>` writes support information offline,
before initializing the host or UI. It reads compiled metadata and embedded source
inputs; changing runtime CI environment variables cannot change the result.

`eng/version-sources.json` owns nine independent axes. AppVersion comes from the
application release, ContractSet from the restored contract schema and descriptor,
and PackageVersion from exact resolved lock entries. Capability, media format,
storage, application policy and extension support remain explicitly not produced;
the catalog names their future owners. Third-party native packages do not establish
a first-party native ABI. These reports do not implement commercial media workflows.

Published Build.Policy 1.0.0-ci.20.1 stamps every owned assembly. Owner targets add
actual dirty state and reject a source mismatch. Build identity records the full
source commit, local/CI kind, run and attempt, pipeline URL and Git source timestamp.
Contracts stays pinned to 1.0.0-ci.36.1; its Hello schema major remains separate.

The repository tool reads actual app/core/test/tool PE metadata. Preparation runs
the compiled AOT app and compares its report with independent source/run/lock inputs.
Archive verification requires the sealed report and rejects tampering even after
an outer archive hash is recomputed. Five native CI hosts retain their existing UI
and real Cloud checks. Public archives and downloaded runtime are verified again.

The immutable `arcnotes-provenance-tools-r2` record describes the reviewed source
adaptation and retains its predecessor and original terms. Mechanism tests mutate
all nine sources independently and reject malformed/aliased/missing sources, wrong
build identity and changed archive members. Synthetic version declarations are
mechanism evidence, not acceptance of future format or compatibility implementations.
