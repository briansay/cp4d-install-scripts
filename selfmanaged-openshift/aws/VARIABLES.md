| Variables             | Default       | Description          |
| --------------------- | :-----------: | -------------------- |
| `region` | us-west-2 | Region where cluster would be deployed. |
| `azlist` | multi_zone | The number of Availability Zones to be used for the deployment. Keep in mind that some Regions may be limited to two Availability Zones. For a IBM Cloud Pak for Data cluster to be highly available, three Availability Zones are needed to avoid a single point of failure. Allowed values: `single_zone` and `multi_zone`. |
| `availability-zone1` | "" | Availability zone values, leave it as it is if you don't want to provide the value, in that case it will be automatically selected based on the region. For `single_zone` installation, provide only `availability-zone1` value. |
| `availability-zone2` | "" | Availability zone values, leave it as it is if you don't want to provide the value, in that case it will be automatically selected based on the region. For `single_zone` installation, provide only `availability-zone1` value. |
| `availability-zone3` | "" | Availability zone values, leave it as it is if you don't want to provide the value, in that case it will be automatically selected based on the region. For `single_zone` installation, provide only `availability-zone1` value. |
| `new-or-existing-vpc-subnet` | new | For existing VPC and SUBNETS use `exist` otherwise use `new` to create a new VPC and SUBNETS, default is `new`. |
| `vpc_cidr` | 10.0.0.0/16 | The CIDR block for the VPC to be created. |
| `cluster_network_cidr` | 10.128.0.0/14 | The CIDR block for the network cidr to be created. |
| `public-subnet-cidr1` | 10.0.0.0/20 | The CIDR block for the public subnet located in Availability Zone 1. |
| `public-subnet-cidr2` | 10.0.16.0/20 | The CIDR block for the public subnet located in Availability Zone 2. |
| `public-subnet-cidr3` | 10.0.32.0/20 | The CIDR block for the public subnet located in Availability Zone 3. |
| `private-subnet-cidr1` | 10.0.128.0/20 | The CIDR block for the private subnet located in Availability Zone 1. |
| `private-subnet-cidr2` | 10.0.144.0/20 | The CIDR block for the private subnet located in Availability Zone 2. |
| `private-subnet-cidr3` | 10.0.160.0/20 | The CIDR block for the private subnet located in Availability Zone 3. |
| `vpcid-existing` | "" | If existing VPC is to be used and selected `exist` as input parameter for `new-or-exist` variable, then provide a VPC id otherwise if creating a new VPC and selected `new` for `new-or-exist` then keep it blank as `??????`. Enable DNS hostnames in existing VPC |
| `only-private-subnets` | "" | Select 'yes' if only private subnets present in the existing VPC, default is 'no'. You should have `ssh` access to the private subnet as bootnode will be created in one of the private subnet. |
| `subnetid-public1` | "" | In case of existing VPC and SUBNETS, Subnet Id for public subnet in zone 1. For `single_zone` installation, provide only `subnetid-public1` and `subnetid-private1` values. For `only-private-subnets` installation, provide all three `private subnet` values or `subnetid-private1` for `single_zone` installation. |
| `subnetid-public2` | "" | In case of existing VPC and SUBNETS, Subnet Id for public subnet in zone 2. For `single_zone` installation, provide only `subnetid-public1` and `subnetid-private1` values. For `only-private-subnets` installation, provide all three `private subnet` values or `subnetid-private1` for `single_zone` installation. |
| `subnetid-public3` | "" | In case of existing VPC and SUBNETS, Subnet Id for public subnet in zone 3. For `single_zone` installation, provide only `subnetid-public1` and `subnetid-private1` values. For `only-private-subnets` installation, provide all three `private subnet` values or `subnetid-private1` for `single_zone` installation. |
| `subnetid-private1` | "" | In case of existing VPC and SUBNETS, Subnet Id for private subnet in zone 1. For `single_zone` installation, provide only `subnetid-public1` and `subnetid-private1` values. For `only-private-subnets` installation, provide all three `private subnet` values or `subnetid-private1` for `single_zone` installation. |
| `subnetid-private2` | "" | In case of existing VPC and SUBNETS, Subnet Id for private subnet in zone 2. For `single_zone` installation, provide only `subnetid-public1` and `subnetid-private1` values. For `only-private-subnets` installation, provide all three `private subnet` values or `subnetid-private1` for `single_zone` installation. |
| `subnetid-private3` | "" | In case of existing VPC and SUBNETS, Subnet Id for private subnet in zone 3. For `single_zone` installation, provide only `subnetid-public1` and `subnetid-private1` values. For `only-private-subnets` installation, provide all three `private subnet` values or `subnetid-private1` for `single_zone` installation. |
| `private-subnet-tag-name` | Requires input | Private subnets Tag Name, all Private Subnets should be Tagged with same Name and Value. |
| `private-subnet-tag-value` | Requires input | Private subnets Tag Value, all Private Subnets should be Tagged with same Name and Value. |
| `key_name` | Requires input | The name of a key pair, which allows you to securely connect to your instance after it launches. |
| `tenancy` | default | Amazon EC2 instances tenancy type, `default / dedicated`. See [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-instance.html) |
| `access_key_id` | Requires input | AWS account access key id for the current user account. |
| `secret_access_key` | Requires input | AWS account secret access key for the current user account. |
| `master_replica_count` | 3 | The desired capacity for the OpenShift master instances. Must be an odd number, a minimum of `3` replica is required for both single and multi zone deployment. |
| `worker_replica_count` | 3 | The desired capacity for the OpenShift worker node instances. Minimum of `3` nodes required. To decide on the number of worker nodes needed check `Resource Requirements for each service` section in [here](../README.md) |
| `master-instance-type` | m5.2xlarge | The EC2 instance type for the OpenShift master instances. Make sure your region supports the selected instance type. Supported master instance types [here](./INSTANCE-TYPES.md) |
| `worker-instance-type` | m5.4xlarge | The EC2 instance type for the OpenShift worker instances. Make sure your region supports the selected instance type.  Supported worker instance types [here](./INSTANCE-TYPES.md) |
| `worker-ocs-instance-type` | m4.4xlarge | The EC2 instance type for the OpenShift container storage (OCS) instances. Make sure your region supports the selected instance type. Supported ocs instance types [here](./INSTANCE-TYPES.md) |
| `bootnode-instance-type` | m5.xlarge | The EC2 instance type for the bootnode instances. |
| `cluster-name` | Requires input  | All resources created by the Openshift Installer will have this name as prefix. |
| `private-or-public-cluster` | public | Public or Private. Set `public` to `private` to deploy a cluster which cannot be accessed from the internet. See [documentation](https://docs.openshift.com/container-platform/4.3/installing/installing_aws/installing-aws-private.html) for more details. |
| `fips-enable` | true | If FIPS mode is enabled, the Red Hat Enterprise Linux CoreOS (RHCOS) machines that OpenShift Container Platform runs on bypass the default Kubernetes cryptography suite and use the cryptography modules that are provided with RHCOS instead. Allowed values `true / false` |
| `admin-username` | ec2-user | Admin username for the bootnode. |
| `openshift-username` | Requires input | Desired Openshift username. |
| `openshift-password` | Requires input | Desired Openshift password. |
| `pull-secret-file-path` | Requires input | The pull secret that you obtained from the [Pull Secret](https://cloud.redhat.com/openshift/install/pull-secret) page on the Red Hat OpenShift Cluster Manager site. You use this pull secret to authenticate with the services that are provided by the included authorities, including Quay.io, which serves the container images for OpenShift Container Platform components. |
| `public_key_path` | Requires input | Path to the ssh public key file to allow terraform run commands remotely. Example: "~/.ssh/id_rsa.pub" |
| `ssh-public-key` | Requires input | ssh Public key to be included in the bootnode and all the nodes in the cluster. Example: "ssh-rsa AAAAB3Nza..." |
| `ssh-private-key-file-path` | Requires input | Path to the private key file of the corresponding ssh public key used to allow terraform run commands remotely. Example: "~/.ssh/id_rsa" |
| `classic-lb-timeout` | 600 | Classic loadbalancer timeout value in seconds. |
| `autoscaler-replica-count` | 1 | Replica count for machine autoscaler. |
| `max-total-nodes` | 24 | Maximum number of node count for cluster autoscaler. |
| `dnszone` | Requires input | The domain name configured for the cluster. |
| `storage-type` | portworx | Storage management to be used for the cp4d installation. Allowed values `portworx / ocs / efs`. |
| `portworx-spec-url` | Requires input | URL for generated portworx specification. Keep `default  = ""` when selecting `storage-type` as `ocs` or `efs`. See [Portworx documentation](PORTWORX.md) for more details. |
| `efs-performance-mode` | Requires input | If storage-type is selected as `efs`, select one of the performance mode, default is `generalPurpose`. Allowed values are `generalPurpose / maxIO`. To read more about efs performance mode see [efs performance modes](https://docs.aws.amazon.com/efs/latest/ug/performance.html#performancemodes) |
| `accept-cpd-license` | reject | Read and accept license at https://ibm.biz/Bdq6KP. Allowed values `accept / reject`. |
| `cpd-namespace` | cpd-tenant | The OpenShift project that will be created for deploying Cloud Pak for Data. It can be any lowercase string. |
| `cpd-external-registry` | Optional | URL for external registry. This is only applicable to install CPD from external registry containing preloaded CPD images. NOTE: The URL should include the namespace (e.g cpd.icr.io/cpd) |
| `cpd-external-username` | Optional | Username for external registry. This is only applicable to install CPD from external registry containing preloaded CPD images. |
| `api-key` | Requires input | Enter the API Key. To generate API Key select [Entitlement Key](https://myibm.ibm.com/products-services/containerlibrary). For external registries, enter password here |
| `data-virtualization` | no | Enter `yes` to install the Data Virtualization Add-on service. If you installing this service, you need to install `data-management-console` service as well. |
| `apache-spark` | no | Enter `yes` to install the Apache Spark Add-on service. |
| `watson-knowledge-catalog` | no | Enter `yes` to install the Watson Knowledge Catalog Add-on service. |
| `watson-studio-library` | no | Enter `yes` to install the Watson Studio Add-on service. |
| `watson-machine-learning` | no | Enter `yes` to install the Watson Machine Learning Add-on service. |
| `watson-ai-openscale` | no | Enter `yes` to install the Watson OpenScale and Watson Machine Learning Add-on services. |
| `cognos-dashboard-embedded` | no | Enter `yes` to install the Cognos dashboard embedded Add-on service. |
| `streams` | no | Enter `yes` to install the Streams Add-on service. |
| `streams-flows` | no | Enter `yes` to install the Streams Flow Add-on service. |
| `datastage` | no | Enter `yes` to install the datastage Add-on service. |
| `db2-warehouse` | no | Enter `yes` to install the DB2Warehouse Add-on service. If you installing this service, you need to install `data-management-console` service as well.  |
| `db2-advanced-edition` | no | Enter `yes` to install the db2 advanced edition Add-on service. If you installing this service, you need to install `data-management-console` service as well. |
| `data-management-console` | no | Enter `yes` to install the data management console Add-on service. |
| `datagate` | no | Enter `yes` to install the Data Gate Add-on service. |
| `decision-optimization` | no | Enter `yes` to install the Decision Optimization Add-on service. |
| `cognos-analytics` | no | Enter `yes` to install the Cognos Analytics Add-on service. |
| `spss-modeler` | no | Enter `yes` to install the SPSS Modeler Add-on service. |
| `db2-bigsql` | no | Enter `yes` to install the Db2 bigaql Add-on service. |
| `planning-analytics` | no | Enter `yes` to install the Planning Analytics Add-on service. |

<!-- | `watson-assistant` | no | Enter `yes` to install the Watson Assistant Add-on service. |
| `watson-discovery` | no | Enter `yes` to install the Watson Discovery Add-on service. |
| `watson-knowledge-studio` | no | Enter `yes` to install the Watson Knowledge Studio Add-on service. |
| `watson-language-translator` | no | Enter `yes` to install the Watson Language Translator Add-on service. |
| `watson-speech` | no | Enter `yes` to install the Watson Speech Add-on service. | -->

