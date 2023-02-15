```
RUST_LOG=debug cargo run
curl http://localhost:8080/users -XPOST -H 'Content-Type: application/json' -d '{ "username": "foo" }'
RUSTFLAGS="--cfg tokio_unstable" cargo build --target wasm32-wasi --release
wasmtime run --tcplisten 127.0.0.1:8080 --env FD_COUNT=3 target/wasm32-wasi/release/wasm-demo.wasm
```
