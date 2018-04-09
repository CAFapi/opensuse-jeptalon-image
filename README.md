# openSUSE and JepTalon image

This project builds on the openSUSE Python2 image [here](https://github.com/CAFapi/opensuse-python2-image), Talon and Jep are then installed on the image. This image can be used as a base by projects which require Python2, Talon and Jep.

### Tini
[Tini](https://github.com/krallin/tini) is pre-installed in the container.  If the image entrypoint is not overwritten then it will be automatically used.

### Startup Scripts
Any executable scripts added to the `/startup/startup.d/` directory will be automatically run each time the container is started (assuming the image entrypoint is not overwritten).

### Certificate Installation
The image comes pre-installed with several startup scripts which provide a mechanism to extend the CA certificates which should be trusted.
