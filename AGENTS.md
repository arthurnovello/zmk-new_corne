Would an agent likely miss this without help?

**Build/Flashing Process:**
The firmware build and flashing must use the `west` toolchain. The process is multi-step: 1) `west build` (referencing specific board/shield combinations defined in `build.yaml`) and 2) `west flash`. Never assume compatibility with standard `corne` builds; the project is specifically for `eyelash_corne`.

**Configuration Source of Truth:**
The entire board and project setup is defined by `config/west.yml`. The specific, required project name is `eyelash_corne`, which must be maintained within the manifest.

**Key Workflow Quirk:**
The project structure requires managing the `boards/arm/eyelash_corne` directory. If integrating into an existing ZMK setup, the module inclusion method is strongly preferred over forking the entire repository.

**Testing/Verification:**
While `build.yaml` shows specific build targets, the assumed standard testing approach for ZMK is executing `west test` after a successful build, ensuring all module dependencies are compiled and tested.