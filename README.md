# KustomizeZPC - Vulnerable by design Kustomize deployment

[![Maintained by Zsclaer-BD-SA Team](https://img.shields.io/badge/maintained%20by-Zscaler--BD--SA%20Team-blue)](https://github.com/zscaler-bd-sa)

![Kustomize](images/kustomize_logo.png)

Demonstrating secure and non secure kubernetes IaC manifests using Kustomize.io (`kubectl -k`) overlays.

## Whats in the repo

The manifests in this respository, demonstrate how to take a basic NGINX kubernetes deployment with many security issues, and use [Zscaler Posture Control (ZPC)](https://www.zscaler.com/products/posture-control) to produce a fully compliant manifest to acheive the same NGINX deployment.

> :warning:  **DO NOT deploy this template examples in a production environment or alongside any sensitive resources.**

> :warning:  **All passwords in this repo are used as an example and should not be used in production**

Using kustomize overlays (environments) we see both forms of these configurations here:

* `kustomize/base` - Our base manifests, *starting* manifests, which are insecure.

* `kustomize/overlays/test` - A few security updates, but still a lot of non compliance.

* `kustomize/overlays/dev` -  An example of an empty overlay, produces the same results as `base` when merged with `kustomize build`

* `kustomize/overlays/prod` - Fully compliant additions to `base`, this overlay renders a clean bill of health when scanned.

## Contributing

Contribution is welcomed!

We would love to hear about more ideas on how to find vulnerable infrastructure-as-code design patterns.

## Zscaler IaC Scanning Projects

* [zpc-aws-cfn-iac-scanning](https://github.com/zscaler-bd-sa/zpc-aws-cfn-iac-scanning) - Vulnerable by design Cloudformation template
* [zpc-terraform-iac-scanning](https://github.com/zscaler-bd-sa/zpc-terraform-iac-scanning) - Vulnerable by design Terraform stack
* [zpc-kustomize-iac-scanning](https://github.com/zscaler-bd-sa/zpc-kustomize-iac-scanning) - Vulnerable by design kustomize deployment
