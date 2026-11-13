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

## Central test_meta source CI

`rosdistro/ros1.yaml` opts `test_meta` into source CI with `test_commits: true`.
The new `.github/workflows/source-ci.yaml` caller polls centrally; test_meta
needs **no AWS/fleet secrets and no workflow hook**. Its test jobs receive only
prepared source and the pinned published feature environment. All artifacts
attach to this toydistro run, not to tailor-meta or test_meta.

Scheduling stays disabled until `SOURCE_CI_ENABLED=true`. Before enabling:

- Provide a trusted `tailor-source-control` runner restricted to configuration
  repositories, with dependency/ECR read and dedicated ledger-prefix write access.
- Configure central secret `SOURCE_CI_GITHUB_TOKEN` (selected source/config reads,
  PR metadata read, commit-status write) and variable `SOURCE_CI_STATE_URI`.
- Publish the feature environment using a source-poll-capable implementation so
  its plan contains pinned test-image digests and its graphs are available.
- Decide artifact privacy: this repository is public. Do not set
  `SOURCE_CI_PUBLIC_INPUTS=true` unless every prepared source/image and log is
  approved for public access. Otherwise use a private configuration repository.

Manual dispatch defaults to dry-run. GitHub schedules/dispatch registration
require the caller on the default branch; enabled feature-branch pushes to the
source-CI caller provide a controlled pilot trigger before cutover. See
tailor-meta's `doc/central-source-ci.md` for limits and acceptance steps. The old
secret-inheriting source-stub dispatch is removed; `test_commits` remains enabled.
