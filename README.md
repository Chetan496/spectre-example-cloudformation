## Sceptre for CloudFormation orchestration

This is a sample POC using Sceptre for CloudFormation orchestration.
Use following commands:
`sceptre create dev/subnets.yaml` - this will first identify that VPC needs to be created first, then it will create subnets
`sceptre delete dev/vpc.yaml`  - this will delete the stacks in expected order

Run above commands from root dir of project.
The config dir has yaml which has parameters and interdependency between the stacks.
Check in `dev/config/subnets.yaml` how the dependency between vpc and subnets is resolved.

In config/dev/vpc.yaml, you can find how a tag is applied based on the environment. refer following:
`Environment: {{ command_path.0 }}`

This is based on a concept called `command paths` in Spectre.

Sceptre documentation is available at:
https://sceptre.cloudreach.com/latest/docs/
