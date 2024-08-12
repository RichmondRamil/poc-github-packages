# poc-github-packages

1. Create Images
2. Create PAT on GitHub
3. Authenticate GHCR
4. Tag and Push our Image to GHCR

```
export CT_PAT=<TOKEN>
echo $CT_PAT | docker login ghcr.io -u USERNAME --password-stdin
```