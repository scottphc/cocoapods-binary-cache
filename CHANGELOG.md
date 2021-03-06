# Changelog

## 0.1.6
### Enhancements
- Remove the `prebuild_all_vendor_pods` option. Specify this in the CLI instead: `pod binary prebuild --all`
- Allow prebuilding specific targets: `pod binary prebuild --targets=A,B,C`
- Provide an option to run code generation for prebuild. Refer to the [`prebuild_code_gen` option](/docs/configure_cocoapods_binary_cache.md).

### Bug fixes
- Exclude files ignored by git when calculating checksums for development pods.
- Exception thrown when `Podfile.lock` is not present https://github.com/grab/cocoapods-binary-cache/issues/20.

---
## 0.1.5
### Enhancements
- Enable device support when prebuild frameworks https://github.com/grab/cocoapods-binary-cache/issues/19. Refer to the [`device_build_enabled` option](/docs/configure_cocoapods_binary_cache.md).

### Bug fixes
None

---
## 0.1.4
### Enhancements
- Allow specifying the prebuild sandbox path (default as `_Prebuild`, previously as `Pods/_Prebuild`).
- Add diagnosis action to spot unintegrated prebuilt frameworks.
- Preparation work for development pods supported.

### Bug fixes
- Missing `push` command in the CLI: `pod binary push`
- Exception thrown when requirements of a pod are not specified https://github.com/grab/cocoapods-binary-cache/pull/17. Kudos to [Mack Hasz](https://github.com/lazyvar).

---
## 0.1.3
### Enhancements
- No need to specify `prebuild_job` in the `config_cocoapods_binary_cache` in a prebuild job.

### Bug fixes
None

---
## 0.1.2
### Enhancements
None

### Bug fixes
- Corrupted cache zip/unzip if there are symlinks inside the framework.

---
## 0.1.1
### Enhancements
- Enhance cache validation mechanism.
- Update DSL: use `config_cocoapods_binary_cache` for cocoapods-binary-cache related configs.
- Validate build settings (for ex. changing a framework from `dynamic` to `static` is considered cache-missed).
- Auto-exclude frameworks with no source (for ex. originally distributed as prebuilt).
- Detect dependencies of pods explicitly declared as prebuilt and treat them as prebuilt.

### Bug fixes
- Various fixes for static frameworks:
  - Resources bundle not integrated properly.
  - XIB resources not integrated properly https://github.com/grab/cocoapods-binary-cache/issues/7.
- Various fixes for cache validation with subspecs.

---
## 0.0.1 - 0.0.5
- Initially released on 2019-12-20 🎉 (0.0.1).
