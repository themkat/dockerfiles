# Ansible-Bender image (working on M1, MacOS)
Experimenting with this because I get errors from [another ansible-bender](https://hub.docker.com/r/jorgeandrada/ansible-bender) image I found online. Errors were due to me using an ARM based machine (M1 MacBook Air)


First build (might put this into a pipeline and push to Docker hub):
```
docker build . -t themkat/ansible-bender:0.1
```

Then run this in the directory you want to use ansible-bender from:
```
docker run --rm --privileged -v /var/run/docker.sock:/var/run/docker.sock -v $PWD:/home/build -it themkat/ansible-bender:0.1 bash
```

Build your image normally with `ansible-bender build playbook.yml`, and then push it to your Docker daemon with `ansible-bender push docker-daemon:testingmctest:0.1` (given that I have built the image testingmctest and want to push it with version/tag 0.1). 


Might be a bit slow, but good to be able to use it on M1 Macs as well :)


*WARNING! You may get some weird errors when images are pulled or similar. It seem to work anyway. Probably just Podman running inside Docker, telling you that it is pulling the image or something*
*Curious n Ansible Bender and want to see some examples? Check out my [blog entry about it](https://themkat.net/2022/03/17/creating_container_images_with_ansible.html)*
