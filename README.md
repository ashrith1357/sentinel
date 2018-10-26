
# Sentinel Policies for Terraform - AWS

Sentinel is an embeddable policy as code framework to enable fine-grained, logic-based policy decisions that can be extended to source external information to make decisions. Infrastructure as code with HashiCorp Terraform enables operators to automate provisioning at scale. This comes with risks, as every action can have larger effects. Sentinel policy as code places guardrails to protect users from creating infrastructure changes that fall outside of business, security, and compliance policies.

## About Policy as Code

Sentinel, the HashiCorp framework for policy as code management, is built to be embedded in existing software to enable fine-grained, logic-based policy decisions. A policy describes under what circumstances certain behaviors are allowed. Sentinel is embedded into the Enterprise version of each of the HashiCorp products and was first introduced at HashiConf. Sentinel basics are covered in: [Terraform Enterprise: Applying policy as code to infrastructure provisioning](https://www.hashicorp.com/blog/sentinel-and-terraform-enterprise-policy-as-code)

Here is the Sentinel documentation aboutwriting policies with the Sentinel language, [the Sentinel documentation](https://docs.hashicorp.com/sentinel/writing/). We can also use the [tfe_sentinel_policy](https://www.terraform.io/docs/providers/tfe/r/sentinel_policy.html) resource from the [Terraform Enterprise provider](https://www.terraform.io/docs/providers/tfe/) to upload a policy using Terraform itself.

# Sentinel and Policy as Code

Sentinel fully embraces policy as code in a number of ways:

    * Language. All Sentinel policies are written using the Sentinel language. This language is made to inputted directly to text files. As an additional benefit, all Sentinel-enabled applications share the same policy language.

    * Development. Sentinel provides a CLI for development and testing. This local CLI can be used to verify policies before deploying them to a system.

    * Testing. Sentinel provides a test framework designed specifically for automation. This allows developers and CI systems to further verify policies.

# Imports

Imports enable Sentinel to access external data and functions.

Sentinel ships with a set of [standard imports](https://docs.hashicorp.com/sentinel/imports/). Standard imports are available by default to every Sentinel policy

To use an import, use the import statement. Then, access data and functions on the import using the import name followed by a period and the field you want to access. The example below checks whether the request path starts with a prefix. Assume that request_path is available.

import "strings"

main = rule { strings.has_prefix(request_path, "/admin") }

