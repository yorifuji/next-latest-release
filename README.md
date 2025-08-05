# next-latest-release

`next-latest-release` is a GitHub Action designed to automate the process of version bumping in software releases. It supports major, minor, and patch version increments, making it easy to retrieve the next version based on the latest GitHub Release.

## Usage

Example workflow:

```yaml
jobs:
  bump:
    runs-on: ubuntu-latest
    steps:
      - uses: yorifuji/next-latest-release@v1
        id: next-latest-release
        with:
          bump: major # major, minor, or patch

      - run: |
          echo "version: ${{ steps.next-latest-release.outputs.version }}"
          echo "version-major: ${{ steps.next-latest-release.outputs.version-major }}"
          echo "version-number: ${{ steps.next-latest-release.outputs.version-number }}"
```

## Outputs

- `version`: The next semantic version number (e.g., `v1.2.3`)
- `major`: The major version number (e.g., `v1`) **[DEPRECATED - use `version-major` instead]**
- `version-major`: The major version number (e.g., `v1`)
- `version-number`: The version number without prefix (e.g., `1.2.3`)

## Development

TBD

### Setup

TBD

### Debug

TBD

## License

MIT
