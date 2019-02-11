# terraform-aws-cloudwatch-to-splunk

Provides a lambda function that forwards logs from cloudwatch to
splunk. This function is configured using [AWS Systems Manager
Parameter
Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-paramstore.html)
(SSM).

TODO: Add more details.

Example Usage
-----------------

```hcl
module "foo" {
  source = "git@github.com:techservicesillinois/terraform-aws-cloudwatch-to-splunk//"
  # NOTE: Normally, callers will NOT specify the function name, except when
  # deploying a test version of the lambda code.
  # function_name = cloudwatch_to_splunk  
}
```

Argument Reference
-----------------

The following arguments are supported:

* `function_name` - Name of the lambda function and role to be deployed
(default: *cloudwatch_to_splunk*)

* `splunk_cache_ttl` - Time-to-live value for cached Splunk connection
in milliseconds (default: *6000*)

* `ssm_prefix` - Prefix string to be applied to look up runtime SSM
variables (default: *cloudwatch_to_splunk*)

Attributes Reference
--------------------

The following attributes are exported:

* `qualified_arn` - The Amazon Resource Name (ARN) identifying your
Lambda function version.
