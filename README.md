> :warning: This project is considered experimental and is not recommended for production use. Functionality may break at any time.

# create-release
Create a Release in the Golioth Cloud with GitHub Actions.

# ✨ Quickstart

To create a release using the latest version of the Golioth CLI:

```yaml
- name: Checkout
  uses: actions/checkout@v4

- name: Setup goliothctl
  uses: golioth/setup-goliothctl@main
  with:
    apiKey: ${{ secrets.APIKEY }}
    projectId: ${{ secrets.PROJECTID }}

- name: Create release
  uses: golioth/create-release@main
  with:
    releaseArtifact: main
    releaseArtifactVersion: 1.0.0
    deviceTag: ci
```

`releaseArtifact` & `releaseArtifactVersion` are required inputs. `setup-goliothctl` requires a Golioth API Key and Project ID. See [golioth/setup-goliothctl](https://github.com/golioth/setup-goliothctl) for more details.

# Inputs

| Parameter | Description | Required |
| --- | --- | --- |
| releaseArtifact | Artifact to use for release. | Yes |
| releaseVersion | Release version to use for release. | Yes |
| deviceTag | Device tag used to restrict a release. | no |