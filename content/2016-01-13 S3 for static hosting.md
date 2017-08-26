Title: S3 for static website hosting
Subtitle: Using AWS S3 for hosting static sites
Slug: s3-for-static-website-hosting
Category: Website
Tags: aws, s3, pelican
Date: 2016-01-13


Yesterday I was attending an AWSome Day conference. Having a good introduction to AWS services I wanted to give S3 a try.

It appears configuring a Pelican instance to work with S3 is very easy. Below's how I did it in less than half an hour.

## Near to zero costs

The amazing thing with static web pages is that you can host them on storage sites. You don't need a web server engine, because there's nothing that needs to be caltulated or transformed. All content is pre-generated.

Due to this fact, you can use storage sites which usually are a much cheaper option than web hosting servers.

S3 is an example; the name stands for Simple Storage Service.

I used the S3 calculator and selected much more resources that I would potentially need:

* 1GB storage,
* 100k GET requests,
* 3k requests of other types

In result I got a [calculated price of... $0.05 per month](http://calculator.s3.amazonaws.com/index.html#r=FRA&s=S3&key=calc-BF4C74D9-B8F6-4C6C-A442-60B3673C7EBD). Yes, 5 cents.


## Setting up S3

I assume you already are a registered user of AWS.

### S3 bucket

First what you need to create is an S3 bucket where your site's files will be stored.

#### Enable website hosting

In the bucket go to `Properties`:

* click `Static Website Hosting`,
* select `Enable website hosting`;
* as Index Document user: `index.html`
* copy or bookmark the Endpoint link - this will be the working domain for your website

### Security credentials

Under your username in the top right corner go to `Security Credentials`. You may be advised to create AWS Identity and Access Management (IAM) users and I strongly recommend to do this. Your AWS account has all priviliges and using it for authorizing a site upload is a security issue.

* Create new user, i.e. "blog"
* Copy security credentials or click "Download Credentials" - this will download a CSV file.
* Click the user name on the list and then click Attach Policy.
* In the filter type `s3full` and attach the shown policy to the user account.

This is it on the AWS side, now let's go back to the local instance of the blog.

## Setting up Pelican


Insert the name of the bucket into `Makefile`:

```bash
S3_BUCKET=your_bucket_name
```

Install `s3cmd` and start configuration:

```bash
pip install s3cmd
s3cmd --configure
```

In the wizard:

* enter `Access Key` from the downloaded `CSV` file
* do the same with `Secret Key`
* choose the region, I switched from `US`, to `EU`
* leave the rest of settings as they are by pressing enter
* test the connection - hopefuly it works fine for you
* save the settings and quit

## Publishing

```bash
make s3_upload
```

## Troubleshooting

If your blog displays with broken paths in your (i.e. no images and no styles) try with setting `RELATIVE_URLS = True` both in `pelicanconf.py` and `publishconf.py`
