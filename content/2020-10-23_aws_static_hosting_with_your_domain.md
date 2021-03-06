Title: My domain for the static website
Subtitle: How to configure your domain for a static website on AWS
Category: cloud
Tags: aws, s3, cloudfront, static website, domain
Date: 2020-10-23

My domain for the static website
================================

(NOTE: I found [an article](https://medium.com/@matthewmanuel/hosting-a-https-static-website-on-amazon-s3-w-cloudfront-and-route-53-f347a16b6a91) which seems to describe the whole solution perfectly well. I'm not going to reinvent the wheel, below are my extra notes for things I had issues with.)

As I am preparing myself to an Software Architect Associate exam, I've decided to undust this blog and make a few improvements.

The first one is linking it to an own domain. Today I've bought `piekarczyk.info`, still available, apparently my last name is not that popular - good for me :)

Quick notes:

  * You need Route54 to set up a hosted zone and an S3 bucket.
  * Yes, it is one hosted zone per domain.
  * Yes, there's a fee for each hosted zone. Currently it costs $.5 per month. This ads +50% to my domain costs ($6 per year, whereas the domain registration/renewal is $12). Not a big deal with a few domains, but can be significant when you have many of them.
  * Yes, you need to name your bucket exactly the same as your domain. So the name of my bucket is dominik.piekarczyk.info.
  * [This document](https://docs.aws.amazon.com/AmazonS3/latest/dev/website-hosting-custom-domain-walkthrough.html) explains very well how to set up your domain and the bucket properly.
  * If you want to have https set up for your website, you need to add CloudFront to the list of tools used. S3 itself does not support HTTPS access.
  * AWS CloudFront documentation should be good enough.
    * There is an SSL certificate which you can add in the form. If you use Route 53 you can set it up on the fly, it takes 2 minutes. Though, I had to refresh the form to have it available on the list.
    * Remember to set index.html as the Default Root Object. Otherwise the domain with the root path (i.e. https://dominik.piekarczyk.info/) will return an access error.

![Scrapy Logo](images/2020-10-24_static_website_aws.png)


I think in the future I will move this blog somewhere else. There are so many convinient solutions out there, where I can easily edit the content online, configure a CI/CD, etc. Though, for the time of preparations to the exam I stick to AWS.

  