

執行 `cargo install --packages docs_preprocessor --debug` 時，遇到以下錯誤：

```bash
   Compiling outline_panel v0.1.0 (/media/hwhsu1231/KubuntuData/Repo/ltdorgtest/zed-docs-l10n/out/repo/crates/outline_panel)
error[E0308]: mismatched types
   --> crates/repl/src/kernels/remote_kernels.rs:177:59
    |
177 |             let kernel_socket = JupyterWebSocket { inner: ws_stream };
    |                                                           ^^^^^^^^^ expected `WebSocketStream<Stream<..., ...>>`, found a different `WebSocketStream<Stream<..., ...>>`
    |
note: two different versions of crate `async_tungstenite` are being used; two types coming from two different versions of the same crate are different types even if they look the same
   --> /home/hwhsu1231/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/async-tungstenite-0.31.0/src/lib.rs:232:1
    |
232 | pub struct WebSocketStream<S> {
    | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ this is the found type `WebSocketStream`
    |
   ::: /home/hwhsu1231/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/async-tungstenite-0.32.0/src/lib.rs:232:1
    |
232 | pub struct WebSocketStream<S> {
    | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ this is the expected type `async_tungstenite::WebSocketStream`
    |
   ::: crates/repl/src/kernels/remote_kernels.rs:6:5
    |
  6 | use async_tungstenite::tokio::connect_async;
    |     ----------------- one version of crate `async_tungstenite` used here, as a direct dependency of the current crate
...
 16 | use jupyter_websocket_client::{
    |     ------------------------ one version of crate `async_tungstenite` used here, as a dependency of crate `jupyter_websocket_client`
    = help: you can use `cargo tree` to explore your dependency tree
    = note: the full name for the type has been written to '/media/hwhsu1231/KubuntuData/Repo/ltdorgtest/zed-docs-l10n/out/repo/target/debug/deps/repl-044dcb9f7ede4cbc.long-type-10991847745054709503.txt'
    = note: consider using `--verbose` to print the full type name to the console

   Compiling project_panel v0.1.0 (/media/hwhsu1231/KubuntuData/Repo/ltdorgtest/zed-docs-l10n/out/repo/crates/project_panel)
For more information about this error, try `rustc --explain E0308`.
error: could not compile `repl` (lib) due to 1 previous error
warning: build failed, waiting for other jobs to finish...
error: failed to compile `docs_preprocessor v0.1.0 (/media/hwhsu1231/KubuntuData/Repo/ltdorgtest/zed-docs-l10n/out/repo/crates/docs_preprocessor)`, intermediate artifacts can be found at `/media/hwhsu1231/KubuntuData/Repo/ltdorgtest/zed-docs-l10n/out/repo/target`.
To reuse those artifacts with a future compilation, set the environment variable `CARGO_TARGET_DIR` to that path.
```

