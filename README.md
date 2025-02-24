# nmk-tmux
Zsh used in nmk-vendor

# upgrade new version from debian

```sh
# Get new version from ubuntu
# At root of repository
dget -x http://deb.debian.org/debian/pool/main/z/zsh/zsh_5.9-8.dsc
rm -rf zsh && mv zsh-5.9 zsh
git add zsh
git commit -m "Upgrade to zsh 5.9-8"
TAG=5.9-8
git tag $TAG
git push && git push --tags
git archive --prefix=zsh-$TAG/ -o zsh-$TAG.tar refs/tags/${TAG}:zsh/
gzip zsh-$TAG.tar
sha256sum -b zsh-$TAG.tar.gz > zsh-$TAG.tar.gz.sha256
```
