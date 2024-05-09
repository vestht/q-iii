# Question 03

## Scenario 01

We can use S3 bucket with CloudFront distribution to host this website. As the question says it's only contain 10 web pages and 500MB in assets so we can easily upload this data to a new S3 bucket.

### Steps:

#### 01. Amazon S3 (Simple Storage Service):

First we need to create a S3 bucket and upload the files of the website to the newly created S3 bucket.

Then we have to enable the static website hosting feature in the S3 configuration to serve our static website as a web page from the S3 bucket.


#### 02. Amazon CloudFront:

Then we need to create a Amazon CloudFront distribution and we need to configure S3 bucket as a resource origin of the CloudFront. Once we complete this CloudFront will load content from the S3 bucket when we request resources from the CloudFront endpoint.

Then we can move into configure the SSL certificate as a custom SSL into the CloudFront configuration and this will allow CloudFront to serve content with SSL bind to our domain name.


#### 03. Amazon Route53:

Finally we need to put a CNAME record in the Route53 hosted zone of the desired domain name pointed to the CloudFront distribution endpoint. This will map the domain name to the CloudFront distribution.


### This configuration will have the following benifits:

**Low management overhead:** Once set up, S3 and CloudFront require minimal maintenance. You only need to upload/update your website assets to the S3 bucket when necessary.

**Cost-effective:** S3 and CloudFront offer a pay-as-you-go pricing model, and for a static website with low to moderate traffic, the costs are typically very low.


## Scenario 02

[TODO]