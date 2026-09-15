# Papaya Actions

Reusable GitHub Actions workflows shared by Papaya repositories.

## Open pull request

Call `.github/workflows/open-pull-request.yml@main` from a repository workflow
triggered by `push` to `feature/**`. The workflow creates one pull request from
the pushed branch to `main` and reuses an existing open pull request on later
pushes.

The caller must grant `pull-requests: write` permission to its `GITHUB_TOKEN`:

```yaml
permissions:
  contents: read
  pull-requests: write

jobs:
  open-pull-request:
    uses: papaya-inc/papaya-actions/.github/workflows/open-pull-request.yml@main
    with:
      base: main
```
