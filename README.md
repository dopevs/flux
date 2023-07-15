# flux
## Install flux components
Install flux cli
```
brew install fluxcd/tap/flux
```
Export github credentials
```
export GITHUB_TOKEN=<your-token>
export GITHUB_USER=<your-username>/<your-org>
```
Check kubernetes cluster
```
flux check --pre
```
Install flux components
```
flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=flux \
  --branch=main \
  --path=./clusters/training \
  --personal --components-extra=image-reflector-controller,image-automation-controller --read-write-key
```
