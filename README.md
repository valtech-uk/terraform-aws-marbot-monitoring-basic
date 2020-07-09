# AWS basics monitoring

Connects you to all relevant sources of errors, warnings, and notifications published by AWS services, and forwards them to Slack or Microsoft Teams managed by [marbot](https://marbot.io/).

## Usage

1. Create a new directory
2. Within the new directory, create a file `main.tf` with the following content:
```
provider "aws" {}

module "marbot-monitoring-basic" {
  source  = "marbot-io/marbot-monitoring-basic/aws"
  #version = "x.y.z"    # we recommend to pin the version

  endpoint_id      = "" # to get this value, select a channel where marbot belongs to and send a message like this: "@marbot show me my endpoint id"
  budget_threshold = 10 # in USD (optional)
}
```
3. Run the following commands:
```
terraform init
terraform apply
```

## Update procedure

1. Update the `version`
2. Run the following commands:
```
terraform get
terraform apply
```

## License
All modules are published under Apache License Version 2.0.

## About
A [marbot.io](https://marbot.io/) project. Engineered by [widdix](https://widdix.net).
