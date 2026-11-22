# Working on Q-HENA

Q-HENA investigates HENA's swarm idea on a quantum substrate, composing Q-MUON units through quantum routing, communication and entanglement-mediated memory. HENA supplies the classical design, Q-MUON the proposed quantum unit and MONAD the formal types. The current repository contains dependency re-exports and a draft paper; no quantum swarm or quantum advantage has been demonstrated here.

Start with the [README](README.md), [build guide](docs/building.md) and [development guide](docs/index.md). Check the [kernel manifest](kernel/Cargo.toml) and [crate root](kernel/src/lib.rs) before treating a proposed interface as implemented.

## Distinguish inheritance from dependencies

HENA is the classical upstream that Q-HENA takes in by merge at each stage, not a current Cargo dependency. `kernel/` directly depends on MONAD, Q-MUON and Reckon. Reckon's repository, package and Rust import are `reckon`, `reckon-kernel` and `reckon_kernel`. `kernel/Cargo.toml` pins each to one commit of its GitHub repository, so a fresh clone builds alone.

The quantum implementations will go in `kernel/qpu/`, which does not exist yet. The protocol headers still live under inherited `protos/hena/` paths and declare no swarm messages. The paper imports MONAD, Q-MUON and Q-HENA definitions; `paper/Q-HENA.tex` is the only paper master.

Q-HENA would own its swarm store and recovery, with Reckon supplying the record protocol. Entanglement alone defines neither a message protocol nor a memory operation. Keep proposed preparations, interactions, measurements and recovery guarantees explicit, and include repeated preparation and failed attempts in comparisons. Restore-mode names and adaptation records in the guide are proposals, not working APIs. The classical and quantum paths remain distinct comparisons.

## Check the kernel crate and the paper

Use Rust and Cargo, with network access for the first fetch of the pinned dependencies. Reckon's default Rust build keeps its Python binding disabled and supplies its Protocol Buffers compiler through Cargo; `PROTOC` can select a compiler explicitly. With the paper tools described in the build guide available, run from this repository's root:

```sh
cargo check --manifest-path kernel/Cargo.toml
(cd paper && make all && ./validate.sh)
```

The Rust check compiles the kernel crate's dependency re-exports; there is no quantum-swarm behavioural test suite. The paper command typesets and validates `paper/Q-HENA.pdf`. Inspect the PDF, warnings and skipped checks; the rendered-text check requires `pdftotext`. These checks establish source integration and typesetting, not emergence, recovery or quantum advantage.

<!-- BEGIN shared repository rules -->

- Review a source file above 1,000 lines and split it by concern before 1,500.
- Keep Rust tests under `tests/`; keep Go's `_test.go` files beside their package.
- Finish a goal with the codebase the same size or smaller unless a requested feature requires growth. Preserve the behaviour, tests, cases and examples.
- Every engine must build from a fresh clone on Linux and macOS.
- Keep generated API reference and build output out of Git; change their source or generator.
- Write comments and API documentation for the code's reader. A crate or module comment first says what it is for in the system, what it builds on and what builds on it, then its purpose, inputs, results and useful edge cases, with the purpose written problem-first in the present tense: the problem it solves and what solves it today. One plain line after that opening says what is not built yet, as the problem now in front of it, and a negative appears only where a reader would expect the opposite: a limit stated as a property of what exists stays ("it runs on loopback with no caller authentication"), while a negative measured against the finished design is a hedge. Keep them self-contained, with links inside the repository.
- Push each repository as one commit whose whole message is `init`, with Harsh as author and committer under the account the folder uses and no `Co-Authored-By` or `Claude-Session` trailers; later commits stay short and plain.
- Describe the present design and research. The repository neither links nor ships lineage: earlier papers, predecessor versions, history tags and the commits behind them.
- Public repository files, including generated text, link within the repository or to public addresses their readers can open.
- A README is the repository's front door: it carries the product account for the technical reader who arrives there, opening with the product's plain name and the problem it solves, in the words its published pages use.
- Name every operation, command, tool, type, field and variable so a reader without its author's context can tell what it does, what it enables and when to use it; docstrings say the same. Keep full-field record schemas for the engine's consistency, named in plain words like everything else, and author each surface's schemas separately, one per intent, in its caller's terms: SDKs and APIs, the command line, the language server and the agent protocols (MCP, A2A, ACP) are different surfaces with different callers, and the agent protocols compose intents over the operations the others expose.
- Write each Markdown paragraph on one source line. Run the repository's formatter with `proseWrap: never` on changed Markdown.

<!-- END shared repository rules -->

Before handing back:

- Are the quantum research question, classical inheritance and actual dependency graph described accurately?
- Are proposed protocols, recovery guarantees and advantage claims distinguished from implemented behaviour?
- Did the relevant checks run, with dependency revisions, warnings, skipped checks and remaining limits stated where they affect the result?
