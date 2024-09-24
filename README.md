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
