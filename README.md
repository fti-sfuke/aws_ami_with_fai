# AWS AMI WITH FAI

This repository aims to build Debian images for aws cloud provider.

## Getting started

You will need a checkout of this repository on your disk and a recent fai-server
package (at least 5.7) installed. Install the necessary fai packages without
the recommends (which avoids turning your host into a DHCP server!).
You also need python3-libcloud from Buster or newer.

```
  # git clone https://github.com/fti-sfuke/aws_ami_with_fai.git
  # sudo apt install --no-install-recommends ca-certificates debsums dosfstools \
    fai-server fai-setup-storage fdisk make python3 python3-libcloud python3-marshmallow \
    python3-pytest python3-yaml qemu-utils udev
```

  Call `make help` and follow the instructions

Example 1:

```
   # make image_bookworm_awsloud_amd64
```

This will create some log output and the following files:

- `image_bookworm_awsloud_amd64.build.json`
- `image_bookworm_awsloud_amd64.info`
- `image_bookworm_awsloud_amd64.raw`
- `image_bookworm_awsloud_amd64.tar`

These images can be used with AWS EC2.


## Supported image type

As shown above, various types of images can be built for different use
cases. Each type of image can be built with the following command:

```
    # make image_<suite>_<type>_<arch>
```

where `<suite>` is one of `buster`, `bullseye`, or `sid`. `<type>` can
be any of the following:

 * `ec2`: Optimized for the Amazon Elastic Compute Cloud (EC2)

## Documentation

 * [Details about creating images](doc/details.md)
 * https://fai-project.org/fai-guide/

