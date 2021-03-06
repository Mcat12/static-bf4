# p4-analyzer
This tool aims to validate various safety properties of [P4] programs.
It does this by first converting P4 code to a [CFG] (Control Flow Graph)
inspired by [GCL], then generating logical predicates which are used to check
the reachability of bugs.

## Build
This project is written in Rust, so first install Rust:
https://www.rust-lang.org/tools/install

There is also a dependency on the [Z3] theorem prover, so install the library
(including header files) either from source or your distribution's package
manager (`z3-devel` for Fedora, `libz3-dev` for Debian systems).

Now that Rust and Z3 are installed, use `cargo` to build the project
(with optimizations):
```
cargo build --release
```

The compiled binary is located at `target/release/p4-analyzer`.

[P4]: https://en.wikipedia.org/wiki/P4_(programming_language)
[CFG]: https://en.wikipedia.org/wiki/Control-flow_graph
[GCL]: https://en.wikipedia.org/wiki/Guarded_Command_Language
[Z3]: https://github.com/Z3Prover/z3