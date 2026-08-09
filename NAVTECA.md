# Navteca downstream patches

This branch is Navteca's maintained distribution of `mattpocock/skills`. It should stay close to upstream and contain only focused team additions.

## Branch and update policy

- Keep `main` as a clean mirror of `mattpocock/skills`.
- Publish tested Navteca behavior from the shared `navteca` branch and keep it as the fork's default installation branch.
- Develop each addition on a short-lived `navteca/*` branch and merge it into `navteca`.
- Merge new `main` releases into `navteca`; do not routinely rebase or force-push the shared branch.
- Send generally useful fixes upstream. Keep organization-specific integration downstream unless upstream accepts a generic extension point.

## Active patch inventory

### Northstar roadmap handoff for Wayfinder

- **Purpose:** Let Wayfinder consume exactly one Northstar `ROADMAP.md` item, create its map on that item's single `Home` tracker, and write the map/context pointer back without taking over portfolio management.
- **Owner:** Navteca product engineering.
- **Files:** `skills/engineering/wayfinder/SKILL.md`, `docs/engineering/wayfinder.md`, `skills/engineering/ask-matt/SKILL.md`.
- **Upstream status:** Downstream-only pending evaluation as a generic roadmap handoff.
- **Removal condition:** Remove if an upstream release provides an equivalent canonical roadmap-item input/output contract.
- **Validation:** Run the repository's normal checks and review the three-file skill/docs diff together.

## Release checklist

1. Fetch upstream and fast-forward mirror `main`.
2. Merge `main` into an integration branch based on `navteca`.
3. Resolve conflicts, update this inventory, and run validation.
4. Merge into `navteca`, push, and test installation in one product repository.
5. Announce behavior changes before changing the team-wide pinned reference.
