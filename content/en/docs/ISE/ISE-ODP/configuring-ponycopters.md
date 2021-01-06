---
title: "DevSecOps FAQ"
linkTitle: "DevSecOps Faq"
date: 2017-01-05
weight: 2
description: >
  DevSecOps Faq
---


# MultiFactor Authentication 


## What will need to have MFA authentication? 

MFA is requirement for ALL authentication point in the system. This generally includes:
1. MFA for cloud console access such as AWS and GCP console ([Recommened Solution](https://gohugo.io))
2. MFA for remote access of EC2 instances and appliances such as RDP and SSH ([Recommened Solution](https://gohugo.io))
3. MFA for web application, web portals etc . ([Recommened Solution](https://gohugo.io))

> Multi-factor authentication (MFA) method should aligns with the Digital Identity Acceptance Statement and NIST 800-63 part B. NIST is encouraging the use of a secure method that does not expose the MFA pin to intercept risk. 

 Acceptable MFA Solution

- [x] PIV
- [x] PIV derived (SAML, OIDC, OAUTH)
- [x] TOTP (e.g., Google Authenticator, Authy)
- [x] HOTP (physical token)
- [x] SMS to registered phone numbers

 Not Acceptable MFA Solution
 - [] Email


 

## Can you give some example of MFA implementation for GSA DevSecOps Teams ?

### For AWS console access  

> 1. AWS native MFA using AWS IAM and virtual MFA device by installing Google Authenticator or Authy app on GSA provided mobile phone.
> 2. MFA using federation using ADFS or OpenAM. FCS uses openam based federation and FCS tenant inherit this by default

### MFA for remote access of EC2

> 1. Controlled access to EC2 instance (SSH, RDP, Web Access etc) through GSA hosted admin VDI, which requires short name token.Access to (SSH, RDP, Web Access etc) should be allowed through only admin VDI.
> 2. Build your own jump server in your environment which requires two factor authentication . This jump server is only entry point to your environment for any remote access. ( Note: We are looking for automation code that building jump server. which forces two factor authentication using piv card or sna token cert etc) 


# Code Examples

## Can i get example of bla bla code ?

Below is example code

```
foo := "bar";
bar := "foo";
```

# GitHub repository 

## What are the link for your repos? 

| What      | Follows         |
|-----------|-----------------|
| A table   | A header        |
| A table   | A header        |
| A table   | A header        |