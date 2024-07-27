ローカルでwrangler devをすると

```
Running custom build: cargo install -q worker-build && worker-build --release
Error: failed to start `cargo metadata`: Permission denied (os error 13)
Caused by: failed to start `cargo metadata`: Permission denied (os error 13)
Caused by: Permission denied (os error 13)
Error: wasm-pack exited with status exit status: 1
```

がでる。

```
sudo chown -R (whoami) ~/.rustup
sudo chown -R (whoami) ~/.cargo
sudo chown -R (whoami) ~/.cargo/bin/worker-build
```

するが効果なし。

dockerで開発したが、deployのときの認証callbackを受け取れない
ports には `- "8976:8976"` を設定済み。

もうちょい調べようと思ったが興味がなくなった。