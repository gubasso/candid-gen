# implement_basic_tests (Issue)

- [ ] canisters_to_gen_candid
  - wrap to a function
  - unit test it
- [x] get_candid_path_str
- [x] get_project_root
- [x] run_command tests
  - [x] refacto run_command integration test, so it tests the real integration
- [x] refactor check_dependencies

```rs
static DFX_CFG: &str = r#"
    {
      "canisters": {
        "counter_backend": {
          "candid": "src/counter_backend/counter_backend.did",
          "declarations": {
            "node_compatibility": true
          },
          "package": "counter_backend",
          "type": "rust"
        },
        "counter_backend2": {
          "candid": "src/counter_backend/counter_backend.did",
          "declarations": {
            "node_compatibility": true
          },
          "package": "counter_backend",
          "type": "rust"
        },
        "counter_backend3": {
          "candid": "src/counter_backend/counter_backend.did",
          "declarations": {
            "node_compatibility": true
          },
          "package": "counter_backend",
          "type": "mokoto"
        },
        "counter_frontend": {
          "dependencies": [
            "counter_backend"
          ],
          "source": [
            "src/counter_frontend/dist"
          ],
          "type": "assets",
          "workspace": "counter_frontend"
        }
      },
      "defaults": {
        "build": {
          "args": "",
          "packtool": ""
        }
      },
      "output_env_file": ".env",
      "version": 1
    }"#;
```