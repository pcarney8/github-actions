# Source-to-Image (S2I) GitHub Action

This action uses [Source2Image](https://github.com/openshift/source-to-image) to build container
images from source. After the image is built, it will automatically be pushed to a desired
image registry.

## Usage

Add the following to a step in your GitHub Workflow:

```yaml
    - uses: redhat-cop/github-actions/deploy@master
      with:
        kube_config: ${{ secrets.KUBE_CONFIG }}
	app_name: example
	namespace: pr-1234
```

If the image registry hosting your builder/base image is public, you may omit `image_pull_registry`,
`image_pull_username` and `image_pull_password`. In keeping with best practice, your credentials
should be stored in secrets and consumed as shown - not added directly to your workflow yaml.

## Credit

This action was originally based on Vadim Rutkovsky's [action-s2i](https://github.com/vrutkovs/action-s2i).
