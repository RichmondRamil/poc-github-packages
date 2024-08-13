# poc-github-packages

1. Create Images
2. Create PAT on GitHub
3. Authenticate GHCR
4. Tag and Push our Image to GHCR

```
export CT_PAT=<TOKEN>
echo $CT_PAT | docker login ghcr.io -u USERNAME --password-stdin
```

Step by Step
1. Build Image in Local Directory
```
dockert build -t <Image_Name> .
```
2. Check Images on Local
```
docker images
```
3. Check if the Image can run
```
docker run <Image_Name>
```
4. Create or Generate PAT/Personal Access Token
```
Github > Settings > Developer Settings > Generate token (Classic) > Give Access Write & Read
```
5. Push Image on Github Container Registry
```
docker tag <Image_Name> ghcr.io/<USERNAME>/<Image_Name>:latest
docket push ghcr.io/<USERNAME>/<Image_Name>
```
6. If the push process denied, you need to authenticate the PAT
```
echo $CT_PAT | docker login ghcr.io -u USERNAME --password-stdin
```