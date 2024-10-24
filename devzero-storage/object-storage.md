---
title: Object Storage
---
# Buckets

DevZero's buckets allow storing a group of objects (with an API compatible with AWS S3).
Buckets are regional in nature and can be access by any workspace in that region.

## Creating a Bucket

Bucket names must be unique across all of DevZero, so we generate bucket names from a prefix you provide

### In your default region

{% code %}
```
$ dz storage bucket create --prefix=my-fancy-bucket
ID                                       Name                                              Region          Status     
bucket-481692276ad14fcf96a32e176d597731  my-fancy-bucket-481692276ad14fcf96a32e176d597731  Portland, USA   Creating  
 
```
{% endcode %}

### In an arbitrary region

{% code %}
```
$ dz storage bucket create --prefix=other-fancy-bucket --region=eu-north-1
ID                                       Name                                                 Region             Status    
bucket-eaed65a5ff9a4a0284d28ad61f962f5f  other-fancy-bucket-eaed65a5ff9a4a0284d28ad61f962f5f  Stockholm, Sweden  Creating  
```
{% endcode %}

## Listing your buckets

{% code %}
```
$ dz storage bucket list
ID                                       Name                                                 Region             Status     
bucket-eaed65a5ff9a4a0284d28ad61f962f5f  my-fancy-bucket-eaed65a5ff9a4a0284d28ad61f962f5f     Portland, USA      Available  
bucket-481692276ad14fcf96a32e176d597731  other-fancy-bucket-481692276ad14fcf96a32e176d597731  Stockholm, Sweden  Available  
```
{% endcode %}

## Accessing a bucket from a workspace
