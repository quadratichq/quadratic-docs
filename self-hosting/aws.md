---
description: Deploy Quadratic to Amazon Web Services (AWS).
---

# AWS

AWS build instructions are for anyone wanting to deploy Quadratic to [Amazon Web Services (AWS)](https://aws.amazon.com/).&#x20;

## Getting started

You'll first need to create a license key from [https://selfhost.quadratichq.com](https://selfhost.quadratichq.com). Quadratic self-hosting is free for individuals and priced per user for business and enterprise users.&#x20;

## CloudFormation

Using Cloud Formation templates is the easiest way to get started with self-hosting Quadratic on AWS.

### Setup

* You'll need a domain where you can configure a subdomain using DNS.
  * Example: `quadratic.yourbusiness.com`&#x20;
* Download the Cloud Formation template that best fits your use-case.
  * [Cloud Formation Templates](https://github.com/quadratichq/quadratic-selfhost/tree/main/deployment/aws/cloudformation)
  * If you don't know which you'd like to use, start with quadratic-selfhost-lite.yml.

### Deployment

1. Go into the AWS Console in the Region where you'd like to deploy Quadratic.
2. Select Cloud Formation and click on the "Create Stack" button.
3. Download a[ Quadratic Cloud Formation Template](https://github.com/quadratichq/quadratic-selfhost/tree/main/deployment/aws/cloudformation).&#x20;
4. Select "Use an existing template" and "Upload a template file", then upload the downloaded template and click on the "Next" button.
5. Name your stack anything you want.
6. Add your [license key](https://selfhost.quadratichq.com/) and the domain or subdomain you plan to host quadratic on for parameters.
   * Example `quadratic.yourbusiness.com`&#x20;
   * We will take care of provisioning SSL certificates on your behalf.
7. &#x20;Click on the "Next" button to continue.
8. On the "Configure stack options" page, no changes are necessary, confirm. Click on the "Next" button to continue.
9. Review options and click on the "Submit" button to launch the stack.
10. Wait for the stack to start.
11. Click on the "Outputs" tab and copy the instance IP address.  Create two DNS A records for your (sub)domain:
    * A  `quadratic.yourbusiness.com` - 192.168.1.1
    * A `*.quadratic.yourbusiness.com` - 192.168.1.1
12. Wait for the DNS to propagate and your stack to start.
13. You're done. Open your subdomain in a web browser (Chome recommended).

## Manual EC2

### Setup

Quadratic is best deployed via an EC2 instance at a minimum of 4 cores and 12 GB of RAM.

### Startup command

Quadratic can be installed via a single command:&#x20;

```
curl -sSf https://raw.githubusercontent.com/quadratichq/quadratic-selfhost/main/init-aws.sh -o init.sh && bash -i init.sh
```

This will download the initialization script, which will prompt for a license key in order to register Quadratic. Enter the license key generated from [https://selfhost.quadratichq.com](https://selfhost.quadratichq.com).

Additionally, the docker compose network will start. Please allow several minutes for the docker images to download.
