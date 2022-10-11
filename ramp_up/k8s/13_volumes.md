# Volumes
**Goals**
- understand concept of volumes and how it is used to persist data
- understand how volumes are mounted to pods

- pods are ephemeral, so how can we get volumes to persist, and how can we map volumes to the right pod after a pod dies and is recreated with different IP
	- In Docker, docker has a way of managing volumes

**Docker Volumes vs Bind Mounts**
- With **Bind Mount**, a file or directory on the _host machine_ is mounted into a container. The file or directory is referenced by its full or relative path on the host machine.
- With **Volume**, a new directory is created **within Docker's storage directory** on the host machine, and **Docker manages** that directory's content.