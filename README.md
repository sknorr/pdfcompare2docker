# pdfcompare2docker

Use the pdfcompare tool, despite it not having been updated past Python 2
WITH THIS ONE WEIRD TRICK!

## Installation

1. Install Docker and docker-compose on your distribution.
   *  OpenSUSE/SLES: `sudo zypper install docker python3-docker-compose`

2. Clone this repository: `git clone https://github.com/sknorr/pdfcompare2docker`


### First-Run Prerequisites

On the first run, Docker or Podman needs to download a container
with an installation of pdfcompare on openSUSE Leap 15.1.

This means, you need:

*  Make sure you have at least 400 MB of space on your root partition left
*  Make sure you have internet access
*  Either have the root password of your machine at the ready or add your user account to the `docker` group


### Creating Output Documents

1. Go to the program directory.
2. Copy both PDFs to the script's directory: `cp /path/to/PDF1.pdf /path/to/PDF2.pdf .`
   Make sure neither of the files you want to compare is called `output.pdf`.
3. Run `docker-compose`:
   * If your user account is a member of the `docker` group: `docker-compose run pdfcompare PDF1.pdf PDF2.pdf`
   * If your user account is not a member of the `docker` group: `sudo docker-compose run pdfcompare PDF1.pdf PDF2.pdf`

(Other options of the script are explained by the tool itself, using `--help`.)

## References

* For the container image itself, see
  [Docker Hub](https://hub.docker.com/r/susedoc/pdfcompare).
* For the container definition, see
  [the doc-ci repository](https://github.com/openSUSE/doc-ci/tree/develop/build-pdfcompare-container).
