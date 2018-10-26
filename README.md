
# Sentinel Policies for Terraform - AWS

Sentinel is an embeddable policy as code framework to enable fine-grained, logic-based policy decisions that can be extended to source external information to make decisions. Infrastructure as code with HashiCorp Terraform enables operators to automate provisioning at scale. This comes with risks, as every action can have larger effects. Sentinel policy as code places guardrails to protect users from creating infrastructure changes that fall outside of business, security, and compliance policies.

## About Policy as Code

Sentinel, the HashiCorp framework for policy as code management, is built to be embedded in existing software to enable fine-grained, logic-based policy decisions. A policy describes under what circumstances certain behaviors are allowed. Sentinel is embedded into the Enterprise version of each of the HashiCorp products and was first introduced at HashiConf. Sentinel basics are covered in: [Terraform Enterprise: Applying policy as code to infrastructure provisioning](https://www.hashicorp.com/blog/sentinel-and-terraform-enterprise-policy-as-code)

Here is the Sentinel documentation aboutwriting policies with the Sentinel language, [the Sentinel documentation](https://docs.hashicorp.com/sentinel/writing/). We can also use the [tfe_sentinel_policy](https://www.terraform.io/docs/providers/tfe/r/sentinel_policy.html) resource from the [Terraform Enterprise provider](https://www.terraform.io/docs/providers/tfe/) to upload a policy using Terraform itself.
