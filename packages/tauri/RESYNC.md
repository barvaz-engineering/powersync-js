# Re-syncing with upstream

This fork tracks `powersync-ja/powersync-js`. Tag scheme for the
`tauri-plugin-powersync` crate: `v<upstream>-lacaja.<n>`
(e.g. `v0.0.3-lacaja.1`, `v0.0.3-lacaja.2`, then `v0.0.4-lacaja.1`).

When upstream publishes a new version of `tauri-plugin-powersync`:

```bash
git remote add upstream https://github.com/powersync-ja/powersync-js
git fetch upstream
git merge upstream/main          # resolve conflicts in packages/tauri/
git tag v<new-upstream>-lacaja.1
git push origin main --tags
```

Then in `lacaja-ai-app`, bump the `rev` in `src-tauri/Cargo.toml`.
