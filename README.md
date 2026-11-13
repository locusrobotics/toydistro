# toydistro

## GitHub Actions pilot

Branch `feature/github-actions-smoke` tests the consolidated implementation in
`locusrobotics/tailor-meta`. `.github/workflows/tailor.yaml` contains only pinned
reusable-workflow calls. Its Jenkins entry point is removed on this branch.

Pushes run hosted configuration validation and real Jammy/Noble packaging smoke
tests. The smoke fixtures exercise ROS 1 → ROS 2 underlays, Debian package/bundle
creation, installation, and execution; they do not build the complete private
distribution. Results, debs, and build identities are uploaded as Actions artifacts.

This pilot uses `validate` mode until buildfarm runners and separate read/write
credentials are configured. Manual dispatch also offers `graph`, `packages`,
and `release`. Normal `feature/*` release policy is automatic publication for
testing; publication approval is a follow-up. Final release labels are immutable.

See tailor-meta's README for credential setup and the publication cutover steps.
