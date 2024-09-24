# Steps to reproduce

1. Open the repository as a VSCode workspace
2. Use the VSCode workspace config to add "test_feat" to the **cargo** feature list
   ```json
   {
       "rust-analyzer.cargo.features": [
           "test_feat"
       ]
   }
   ```
4. Observe error: crate test2 doesn't have this feature.
   ```
   `cargo metadata` exited with an error: error: none of the selected packages contains these features: test_feat
   ```
5. Try to resolve: add a rust-analyzer.toml file in crate test1 with contents:
   ```toml
   cargo.features = ["test_feat"]
   ```
   and observe as it has no effect because `cargo.features` is a *workspace-level* config and not *crate-level*
