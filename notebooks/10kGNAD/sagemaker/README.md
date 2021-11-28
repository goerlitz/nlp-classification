# Sagemaker Notebooks

## GPU Pricing

Recommended GPU instances: G3, G4, P3, P4
https://docs.aws.amazon.com/dlami/latest/devguide/gpu.html
https://aws.amazon.com/sagemaker/pricing/

|-----------------|----|-------|-------|
| ml.p3.2xlarge |	8|	61 GiB|	$3.825|
| ml.p3.8xlarge |	32|	244 GiB|	$14.688|
| ml.p3.16xlarge |	64|	488 GiB|	$28.152|
| ml.p3dn.24xlarge |	96|	768 GiB|	$35.894|
| ml.g4dn.xlarge |	4|	16 GiB|	$0.7364|
| ml.g4dn.2xlarge |	8|	32 GiB|	$0.94|
| ml.g4dn.4xlarge |	16|	64 GiB|	$1.505|
| ml.g4dn.8xlarge |	32|	128 GiB|	$2.72|
| ml.g4dn.12xlarge |	48|	192 GiB|	$4.89|
| ml.g4dn.16xlarge |	64|	256 GiB|	$5.44|

https://stackoverflow.com/questions/60868257/aws-sagemaker-on-gpu
-> p2.xlarge (NVIDIA K80) or p3.2xlarge (NVIDIA V100)

ResourceLimitExceeded: An error occurred (ResourceLimitExceeded) when calling the CreateTrainingJob operation: The account-level service limit 'ml.g4dn.2xlarge for training job usage' is 0 Instances, with current utilization of 0 Instances and a request delta of 1 Instances. Please contact AWS support to request an increase for this limit.

->
* https://aws.amazon.com/premiumsupport/knowledge-center/resourcelimitexceeded-sagemaker/
* https://docs.aws.amazon.com/general/latest/gr/sagemaker.html#limits_sagemaker