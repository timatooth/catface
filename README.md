# catscanface 😺
> Detect motion and cat faces with Raspberry Pi, OpenCV & AWS Lambda

Contains Raspberry Pi agent for uploading motion detected frames to S3 which triggers a Python lambda function
for doing further cat Haar Cascade facial processing.

Makes optional use of Datadog for statsd metrics & Raspberry Pi Sense Hat.

## Raspberry Pi Agent usage
Configuration can be set on the command line or via environment variables. Usage of S3 requires AWS client ID & secrets
to be configured.

    usage: agent.py [-h] [--resolution RESOLUTION] [--fps FPS]
                    [--delta-threshold DELTA_THRESHOLD] [--min-area MIN_AREA]
                    [--enable-sensehat] [--enable-statsd] [--enable-annotate]
                    [--image-path IMAGE_PATH] [--enable-s3]
                    [--s3-bucket S3_BUCKET] [--s3-prefix S3_PREFIX]

    Motion detect and upload frames to S3

    optional arguments:
      -h, --help            show this help message and exit
      --resolution RESOLUTION
                            e.g 640x480
      --fps FPS             Framerate e.g: 18
      --delta-threshold DELTA_THRESHOLD
      --min-area MIN_AREA
      --enable-sensehat     Use Sense Hat display
      --enable-statsd       Send metrics
      --enable-annotate     Draw detected regions to image
      --image-path IMAGE_PATH
                            Where to save images locally eg /tmp
      --enable-s3           Enable saving frames to AWS S3
      --s3-bucket S3_BUCKET
                            AWS S3 bucket to save frames
      --s3-prefix S3_PREFIX
                            AWS S3 bucket prefix path e.g cats/

#### Requirements
OpenCV on Raspberry Pi

```apt-get install libopencv-dev python-opencv python-dev```

pip dependencies for AWS & Datadog

```pip install boto3 dogstatsd```

## AWS Lambda Function for Haar Cascade facial recognition:
TODO
