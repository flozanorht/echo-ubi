# echo-ubi

Minimal "hello, world" container image based on Red Hat's Universal Base Image (UBI).
For more information about UBI, see: https://www.redhat.com/en/blog/introducing-red-hat-universal-base-image

This is NOT a long-running container, it just just echoes a greeting and terminates.

You need a Red Hat Developer's account to grab the service account user name and token to download the UBI base images. It is free. :-)
You can also use the unauthenticated registry while it is still available.

Register at https://developers.redhat.com and, while logged in to the Developer's web site, access https://access.redhat.com/terms-based-registry/ to create your registry service account.

On RHEL 7.6+, CentOS, and Fedora, you do:

```
$ sudo podman login -u <your service account name> -p <your service account token>
$ sudo podman build -t echo .
$ sudo podman run --name echo localhost/echo
Hello, world
$ sudo podman rm echo
```

You could use the docker command but I like podman more.
I suppose it is available from other Linux distros, I don't know about Windows and MacOS.

