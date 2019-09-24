## docker volume 常见命令
- docker volume create my-vol #Create a volume
- docker volume ls # Volume list
- docker volume inspect my-vol # inspect the volume
- docker volume rm my-vol # remove my-vol
- docker run -d --name devtest -v myvol2:/app nginx:latest # Start a container with a volume
- docker service create -d --replicas=4  --name devtest-service --mount source=myvol2,target=/app  nginx:latest # Start a service with volumes
- docker run -d --name=nginxtest -v nginx-vol:/usr/share/nginx/html:ro nginx:latest # Use a read-only volume
- docker volume create --driver vieux/sshfs -o sshcmd=test@node2:/home/test -o password=testpassword sshvolume # Create a volume using a volume driver
- docker run -d \
  --name sshfs-container \
  --volume-driver vieux/sshfs \
  --mount src=sshvolume,target=/app,volume-opt=sshcmd=test@node2:/home/test,volume-opt=password=testpassword \
  nginx:latest