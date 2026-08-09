# Navteca downstream patches

This branch is Navteca's maintained distribution of `mattpocock/skills`. It should stay close to upstream and contain only focused team additions.

## Branch and update policy

- Keep `main` as a clean mirror of `mattpocock/skills`.
- Publish tested Navteca behavior from the shared `navteca` branch and keep it as the fork's default installation branch.
- Develop each addition on a short-lived `navteca/*` branch and merge it into `navteca`.
- Merge new `main` releases into `navteca`; do not routinely rebase or force-push the shared branch.
- Send generally useful fixes upstream. Keep organization-specific integration downstream unless upstream accepts a generic extension point.

The weekly and manually dispatchable `Sync upstream` workflow fast-forwards the clean `main` mirror, merges new upstream commits on `sync/upstream-main`, and opens a pull request into `navteca`. It never merges into the downstream branch unattended. Merge conflicts fail the workflow and require a maintainer to resolve them explicitly.

`navteca` is protected: changes require a pull request, one approval, resolution of review conversations, and approval from someone other than the latest pusher. Force-pushes and branch deletion are disabled.

## Active patch inventory

### Northstar roadmap handoff for Wayfinder

- **Purpose:** Let Wayfinder consume exactly one Northstar `ROADMAP.md` item, create its map on that item's single `Home` tracker, and write the map/context pointer back without taking over portfolio management.
- **Owner:** Navteca product engineering.
- **Files:** `skills/engineering/wayfinder/SKILL.md`, `docs/engineering/wayfinder.md`, `skills/engineering/ask-matt/SKILL.md`.
- **Upstream status:** Downstream-only pending evaluation as a generic roadmap handoff.
- **Removal condition:** Remove if an upstream release provides an equivalent canonical roadmap-item input/output contract.
- **Validation:** Run the repository's normal checks and review the three-file skill/docs diff together.

## Release checklist

1. Review the automated `sync/upstream-main` pull request, or dispatch `Sync upstream` manually when an update cannot wait for Monday.
2. Resolve conflicts explicitly and update this inventory when a patch changes or becomes removable.
3. Run repository validation and review every promoted skill together with its public documentation.
4. Obtain approval, merge into `navteca`, and test installation in one product repository.
5. Announce behavior changes before updating the team-wide installation.
