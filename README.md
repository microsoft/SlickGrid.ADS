This project is a clone of https://github.com/6pac/SlickGrid with customizations made for use in Azure Data Studio.

## Release Process

Releases are automated with the GitHub Actions workflow at `.github/workflows/release.yml`.

### Automatic release trigger

When `package.json` is changed on `main`, the workflow checks whether the `version` value changed.
If the version changed and a matching `v<version>` tag does not already exist, it automatically:

- Creates and pushes the `v<version>` tag
- Creates a GitHub Release with generated notes
- Attaches the npm package tarball (`.tgz`) to the release

### How to create a release

1. Open **Actions** in GitHub and run the **Release** workflow.
2. Provide a semantic version (for example, `2.3.52`, without `v`).

The workflow will:

- Update `package.json` version
- Commit the version bump to `main`
- Create and push a `v<version>` tag
- Create a GitHub Release with generated notes
- Attach the npm package tarball (`.tgz`) to the release
