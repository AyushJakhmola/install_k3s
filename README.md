# ![AWS Infra to create k3s cluster](project-logo.png)

This repo is functionality complete — PRs and issues welcome!

# Getting started

To get the Node server running locally:


- Clone this repo
- `terraform init` to install all required module source
- `terraform plan and apply` to see the resources to be create and to create infra on AWS

# Code Overview

## Dependencies

- [terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) - To install terraform.
- [packer](https://www.packer.io/) - To install packer.
- [AWS cli](https://docs.aws.amazon.com/cli/v1/userguide/cli-chap-install.html) - to install aws cli only if you are configuring AWS credentials.

## Application Structure



## Error Handling

In `routes/api/index.js`, we define a error-handling middleware for handling Mongoose's `ValidationError`. This middleware will respond with a 422 status code and format the response to have [error messages the clients can understand](https://github.com/gothinkster/realworld/blob/master/API.md#errors-and-status-codes)

## Authentication

Requests are authenticated using the `Authorization` header with a valid JWT. We define two express middlewares in `routes/auth.js` that can be used to authenticate requests. The `required` middleware configures the `express-jwt` middleware using our application's secret and will return a 401 status code if the request cannot be authenticated. The payload of the JWT can then be accessed from `req.payload` in the endpoint. The `optional` middleware configures the `express-jwt` in the same way as `required`, but will *not* return a 401 status code if the request cannot be authenticated.


<br />

[![Brought to you by Ayush Jakhmola]
