# AGENTS.md

This repository is the working root for Urchin ZMK firmware changes.

## Working Directory

- Always work in `/mnt/c/users/rlawl/urchin-zmk-firmware`.
- Do not make firmware changes in `/mnt/c/users/rlawl/��urchin` unless explicitly asked.

## Main Files

- `config/urchin.keymap`: main key layout and layer definitions.
- `config/urchin.conf`: keyboard firmware options.
- `build.yaml`: GitHub Actions build matrix.
- `config/west.yml`: ZMK module dependencies.
- `config/urchin.json`: keymap editor metadata.

## Expected Workflow

- Default task is editing `config/urchin.keymap`.
- Keep the layout US-keycode based unless the user explicitly asks for another locale.
- Prefer minimal edits that preserve the existing layer structure.
- If changing symbol keys, use standard ZMK keycodes from `dt-bindings/zmk/keys.h`.
- Do not reintroduce `keymap_italian.h` unless the user explicitly asks for the Italian layout.

## Build And Publish

- This repo builds firmware through GitHub Actions, not local compilation by default.
- Pushes to the user's fork can trigger the build workflow in `.github/workflows/build.yml`.
- If the workflow does not auto-start on a fresh fork, check Actions indexing and use `workflow_dispatch`.

## Git Safety

- Stage only files related to the requested keymap or firmware change.
- Do not rewrite unrelated history.
- Prefer working on a branch instead of pushing unreviewed changes directly.
