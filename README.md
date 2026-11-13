# toydistro

## GitHub Actions pilot

Branch `feature/github-actions-smoke` tests the consolidated implementation in
`locusrobotics/tailor-meta`. `.github/workflows/tailor.yaml` contains only pinned
reusable-workflow calls. Its Jenkins entry point is removed on this branch.

Pushes call the unified hosted CI and generic toolchain image factory. Target OSes
come only from `config/recipes.yaml`; tailor-meta has no target OS matrix.
Builder images live under the single `ghcr.io/locusrobotics/toydistro` package,
tagged `builder-<implementation-sha>-<os>`. No new Git repositories are created.
The smoke fixtures use the same production
builder and `build-os` command to exercise ROS 1 → ROS 2 underlays, Debian package/bundle
creation, installation, and execution; they do not build the complete private
distribution. Results, debs, and build identities are uploaded as Actions artifacts.

This pilot runs hosted CI until buildfarm runners and separate read/write
credentials are configured. Manual dispatch also offers `graph`, `packages`,
and `release`. Normal `feature/*` release policy is automatic publication for
testing; publication approval is a follow-up. Final release labels are immutable.

Make the GHCR builder package public before buildfarm cutover. See tailor-meta's
README for credential setup and publication steps. Generic tools/imager images
are shared; they do not select this repository's target OSes.
