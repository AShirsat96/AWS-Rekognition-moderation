# AWS Rekognition Image Moderation

A Python implementation for detecting inappropriate content in images using AWS Rekognition's image moderation feature. This implementation analyzes images stored in S3 buckets for potentially inappropriate or offensive content.

## Features

- Detects inappropriate content in images
- Provides confidence scores for detected content
- Works with images stored in S3 buckets

## Prerequisites

- Python 3.8.8
- boto3 (AWS SDK for Python)
- AWS Account with Rekognition and S3 access
- AWS Access Key and Secret Access Key
- S3 bucket containing images to analyze

## Installation

Install the required AWS SDK for Python:

```bash
pip install boto3
```

## Configuration

You'll need to configure the following AWS credentials:

```python
aws_accesskey = <Your Access Key>
aws_secretaccess = <Your secret access key>
myregion = <your region>
```

## Required Libraries
```python
import boto3
```

## Usage

The main functionality is provided through the `Moderate_Image` function:

```python
Moderate_Image(aws_access, aws_secret, aws_region, photo_name, bucket_name)
```

### Parameters

- `aws_access`: Your AWS access key ID
- `aws_secret`: Your AWS secret access key
- `aws_region`: AWS region for Rekognition service
- `photo_name`: Name of the image file in the S3 bucket
- `bucket_name`: Name of the S3 bucket containing the image

### Return Value

Returns the number of moderation labels detected in the image (integer).

### Output Format

For each detected moderation label, the function prints:
- Label name
- Confidence score
- Parent category name

Example output:
```
Detected labels for Smoking.jpg
Smoking : 96.02770233154297
Drug & Tobacco Paraphernalia & Use
Drug & Tobacco Paraphernalia & Use : 96.02770233154297
Drugs & Tobacco
Drugs & Tobacco : 96.02770233154297
```

## Example Usage

```python
# Analyze an image for inappropriate content
label_count = Moderate_Image(
    aws_accesskey,
    aws_secretaccess,
    myregion,
    'image.jpg',
    'your-bucket-name'
)

# The function returns 0 if no inappropriate content is detected
# Returns positive integer if moderation labels are found
```



