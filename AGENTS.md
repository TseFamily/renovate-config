# Repository Instructions

Start with `PROJECT.md` and `.doctrine/project.json` before changing this
repository. They define the project goal, lifecycle, boundaries, public
surfaces, delivery model, and adoption gaps.

Use `SylphxAI/doctrine` for enterprise standards. Keep this repository a relay:
base Renovate policy belongs in `SylphxAI/renovate-config`, while
repo-specific exceptions belong in the consuming repository unless intentionally
family-wide.

For control-plane-only changes, validate with:

```bash
python3 /Users/kyle/.doctrine/scripts/project-control-plane-audit.py --local . --fail-on-drift --json
git diff --check
```

For Renovate policy changes, also validate JSON and prove affected preset
resolution or Renovate dry-run behavior.
