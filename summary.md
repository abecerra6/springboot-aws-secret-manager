# Summary

This small spring-boot application has two profiles: 1) a deployment in EC2, 2) a local one

The first profile for EC2 uses a secret we have in AWS secrets manager:

https://github.com/abecerra6/springboot-aws-secret-manager/blob/810077593eeb4bc5599ab565d5bc087531147d75/src/main/resources/bootstrap.yml#L3

The second profile deactivates aws secrets manager:

https://github.com/abecerra6/springboot-aws-secret-manager/blob/master/src/main/resources/bootstrap-local.yml

And defines the secret in:

https://github.com/abecerra6/springboot-aws-secret-manager/blob/810077593eeb4bc5599ab565d5bc087531147d75/src/main/resources/application-local.yml#L2

When the app starts with the local profile the secret is the one defined above. 
When the app starts with the profile for EC2 deployment the secret is fetched from AWS secrets manager at boot time and used.

## For webapp and event

For usage in VEP applications there is an open question:

Can we use the aws-secrets-manager artifact without using spring-boot?, or boot takes care of the secrets injection?

We also have to start using profiles


