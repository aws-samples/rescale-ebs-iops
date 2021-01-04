# Rescaling EBS volumes programmatically

This code sample is discussed in detail in this AWS [blog post](https://aws.amazon.com/es/blogs/aws-spanish/administrando-la-capacidad-de-entrada-salida-de-volumenes-ebs-de-manera-programatica/).

## Usage

#### Pre-requisites

- An AWS Account.
- An EBS volume attached to an EC2 instance.
- IAM Privileges to deploy the components of this solution.

#### Deployment

1 - Clone the code in this repository.

2 - Proceed with the following commands in the terminal.

```
aws cloudformation create-stack --stack-name RescaleEBSIOPs --template-body file://rescale-ebs-iops.yaml --capabilities CAPABILITY_IAM
```

3 - Validate the deployment: refer to this [blog post](https://aws.amazon.com/es/blogs/aws-spanish/administrando-la-capacidad-de-entrada-salida-de-volumenes-ebs-de-manera-programatica/) for further instructions.

#### Cleanup

In order to delete all the components deployed within this solution and so avoid additional charges:

1 - Run the following commands in your terminal:

```
aws cloudformation delete-stack --stack-name RescaleEBSIOPs
```

2 - (Optional) Open the EC2 console and identify/delete unnecessary EBS snapshots created by this solution (they are tagged as 'Rescale IOPs snapshot').

3 - (Optional) Delete CloudWatch log streams: /aws/lambda/RescaleEBS-\*

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.
