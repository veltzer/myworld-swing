# TOFIX

Findings from a code scan on 2026-10-04.

## Medium

- `README.md:2` - claims "Swing interface to the myworld database" but the repo has never contained any Java/Swing code (git history is only `.gitignore`/LICENSE/tag-file churn and a deleted Makefile). Either implement the Swing client or mark the README as a placeholder/planned project so it does not advertise something that does not exist.
- repo root - no `rsconstruct.toml` and no `.github/workflows/build.yml`, so nothing (not even `README.md` via rumdl, or `config/project.lua` via luacheck) is checked in CI, unlike sibling `myworld-gtk`. Add the minimal fleet `rsconstruct.toml` (rumdl on `README.md`, taplo) plus the shared `build.yml` and `.github/dependabot.yml`.

## Low

- `README.md:1` - hand-written README while most fleet repos generate it from `tera.templates/README.md.tera` + `config/project.lua`; adopt the shared template (needs `config/personal.lua`, `config/version.lua`, and a tera processor) once the repo has a build.
