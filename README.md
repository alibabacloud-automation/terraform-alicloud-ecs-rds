Alicloud ECS&RDS Terraform Module On Alibaba Cloud

terraform-alicloud-ecs-rds
---


Terraform module which creates ECS&RDS instance on Alibaba Cloud.

These types of resources are supported:

* [alicloud_instance](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/instance)
* [alicloud_db_instance](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/db_instance)

----------------------

Usage
-----
You can use this in your terraform template with the following steps.

1. Adding a module resource to your template, e.g., main.tf

    ```
       module "ecs-rds" {
       source            = "../"
       name              = "tf-ecs-rds"
       instance_type     = "ecs.n4.large"
       rds_instance_type = "rds.mysql.s2.large"
       }
    ```

2. Setting `access_key` and `secret_key` values through environment variables:

    - ALICLOUD_ACCESS_KEY
    - ALICLOUD_SECRET_KEY
    - ALICLOUD_REGION

## Inputs

| Name | Description | Type | Required | Default |
|------|-------------|:----:|:-----:|:-----:|
| name | The specification of module name. | string | yes | `tf-ecs-rds` | 
| description | The specification of module description. | string | no | `tf-ecs-rds-description` |
| available_disk_category | The specification of available disk category. | string | no | `cloud_efficiency` |
| available_resource_creation | The specification of available resource creation. | string | no | `VSwitch` |
| vpc_cidr_block | The specification of the vpc cidr block. | string | no | `192.168.0.0/16` |
| vswitch_cidr_block | The specification of the vswitch cidr block. | string | no | `192.168.1.0/24` |
| instance_type | The specification of the instance type. | string | no | `ecs.n4.large` |
| system_disk_category | The specification of the system disk category. | string | no | `cloud_efficiency` |
| system_disk_name | The specification of the system disk name. | string | no | `system_disk` |
| system_disk_description | The specification of the system disk description. | string | no | `system_disk_description` |
| image_id | The specification of the image id. | string | no | `ubuntu_18_04_64_20G_alibase_20190624.vhd` |
| internet_max_bandwidth_out | The specification of the internet max bandwidth out. | number | no | `10` |
| ecs_size | The specification of the ecs size. | number | no | `1200` |
| category | The specification of the category. | string | no | `cloud_efficiency` |
| engine | The specification of the engine. | string | no | `MySQL` |
| engine_version | The specification of the engine version. | string | no | `5.6` |
| rds_instance_type | The specification of the rds instance type. | string | no | `rds.mysql.s2.large` |
| instance_storage | The specification of the instance storage. | number | no | `30` |
| instance_charge_type | The specification of the instance charge type. | string | no | `Postpaid` |
| monitoring_period | The specification of the monitoring period. | number | no | `60` |

## Outputs

| Name | Description |
|------|-------------|
| this_vpc_id | The VPC instance ID |
| this_vswitch_id | The VSwitch ID |
| this_security_group_id | The security group ID |
| this_ecs_id | The ECS instance ID |
| this_rds_id | The RDS instance ID |

Authors
-------
Created and maintained by He Guimin(@xiaozhu36, heguimin36@163.com)

Reference
---------

* [Terraform-Provider-Alicloud Github](https://github.com/terraform-providers/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://www.terraform.io/docs/providers/alicloud/index.html)
