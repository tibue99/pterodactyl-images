# Pterodactyl Docker Images

Docker images for Pterodactyl, created on top of images from [Software-Noob](https://github.com/Software-Noob/pterodactyl-images), 
[Parkervcp](https://github.com/parkervcp/images), [Matthewpi](https://github.com/matthewpi/images) and [Yolks](https://github.com/pterodactyl/yolks).

## Guide

1. Create a personal access token on GitHub with the `write:packages` and `delete:packages` scope.
2. Start `Docker Desktop`
3. In the WSL workspace: 
    ```
    export CR_PAT=TOKEN
    echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin
    ```
4. Navigate to the directory of the Dockerfile and build the image. 
   To access windows files in the WSL, navigate to the wsl root, then navigate in the `mnt` folder.
   ```
   docker build -t ghcr.io/USERNAME/IMAGE:TAG .
   ```
   The image should now show up in `Docker Desktop`. 
   Make sure that line separators are set to `LF` for `entrypoint.sh`.
5. Push the image to GitHub.
    ```
    docker push ghcr.io/USERNAME/IMAGE:TAG
    ```
