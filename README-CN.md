Terraform module which creates lightweight web service with ECS&RDS on Alibaba Cloud

terraform-alicloud-ecs-rds
=====================================================================

[English](README.md) | 简体中文

本 Module 用于在阿里云的 VPC 下创建一个轻量级 WEB 服务，包含：`ECS`、 `RDS`。

本 Module 支持创建以下资源:

* [alicloud_instance](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/instance)
* [alicloud_db_instance](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/db_instance)

## 用法

```hcl
module "example" {
  source            = "terraform-alicloud-modules/ecs-rds/alicloud"
  name              = "tf-ecs-rds"
  instance_type     = "ecs.n4.large"
  rds_instance_type = "rds.mysql.s2.large"
}
```

## 注意事项

* 本 Module 使用的 AccessKey 和 SecretKey 可以直接从 `profile` 和 `shared_credentials_file`
  中获取。如果未设置，可通过下载安装 [aliyun-cli](https://github.com/aliyun/aliyun-cli#installation) 后进行配置.

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_alicloud"></a> [alicloud](#provider\_alicloud) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [alicloud_db_instance.default](https://registry.terraform.io/providers/hashicorp/alicloud/latest/docs/resources/db_instance) | resource |
| [alicloud_instance.default](https://registry.terraform.io/providers/hashicorp/alicloud/latest/docs/resources/instance) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_availability_zone"></a> [availability\_zone](#input\_availability\_zone) | The available zone to launch modules. | `string` | `""` | no |
| <a name="input_category"></a> [category](#input\_category) | The specification of the category. | `string` | `"cloud_efficiency"` | no |
| <a name="input_data_disks_name"></a> [data\_disks\_name](#input\_data\_disks\_name) | The name of the data disk. | `string` | `""` | no |
| <a name="input_description"></a> [description](#input\_description) | The specification of module description. | `string` | `""` | no |
| <a name="input_ecs_size"></a> [ecs\_size](#input\_ecs\_size) | The specification of the ecs size. | `number` | `1200` | no |
| <a name="input_encrypted"></a> [encrypted](#input\_encrypted) | Encrypted the data in this disk. | `bool` | `false` | no |
| <a name="input_engine"></a> [engine](#input\_engine) | Database type. | `string` | `"MySQL"` | no |
| <a name="input_engine_version"></a> [engine\_version](#input\_engine\_version) | The specification of the engine version. | `string` | `"5.6"` | no |
| <a name="input_image_id"></a> [image\_id](#input\_image\_id) | The specification of the image id. | `string` | `""` | no |
| <a name="input_instance_charge_type"></a> [instance\_charge\_type](#input\_instance\_charge\_type) | The specification of the instance charge type. | `string` | `"Postpaid"` | no |
| <a name="input_instance_storage"></a> [instance\_storage](#input\_instance\_storage) | The specification of the instance storage. | `string` | `"30"` | no |
| <a name="input_instance_type"></a> [instance\_type](#input\_instance\_type) | The specification of the instance type. | `string` | `""` | no |
| <a name="input_internet_max_bandwidth_out"></a> [internet\_max\_bandwidth\_out](#input\_internet\_max\_bandwidth\_out) | The specification of the internet max bandwidth out. | `number` | `10` | no |
| <a name="input_monitoring_period"></a> [monitoring\_period](#input\_monitoring\_period) | The specification of the monitoring period. | `string` | `"60"` | no |
| <a name="input_name"></a> [name](#input\_name) | The specification of module name. | `string` | `""` | no |
| <a name="input_rds_instance_type"></a> [rds\_instance\_type](#input\_rds\_instance\_type) | The specification of the rds instance type. | `string` | `""` | no |
| <a name="input_security_group_ids"></a> [security\_group\_ids](#input\_security\_group\_ids) | A list of security group ids to associate with. | `list(string)` | `[]` | no |
| <a name="input_system_disk_category"></a> [system\_disk\_category](#input\_system\_disk\_category) | The specification of the system disk category. | `string` | `"cloud_efficiency"` | no |
| <a name="input_system_disk_description"></a> [system\_disk\_description](#input\_system\_disk\_description) | The specification of the system disk description. | `string` | `""` | no |
| <a name="input_system_disk_name"></a> [system\_disk\_name](#input\_system\_disk\_name) | The specification of the system disk name. | `string` | `""` | no |
| <a name="input_vswitch_id"></a> [vswitch\_id](#input\_vswitch\_id) | VSwitch variables, if vswitch\_id is empty, then the net\_type = classic. | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_this_ecs_id"></a> [this\_ecs\_id](#output\_this\_ecs\_id) | The ID of the ECS instance. |
| <a name="output_this_ecs_name"></a> [this\_ecs\_name](#output\_this\_ecs\_name) | The name of the ECS instance. |
| <a name="output_this_rds_id"></a> [this\_rds\_id](#output\_this\_rds\_id) | The ID of the RDS instance. |
| <a name="output_this_rds_name"></a> [this\_rds\_name](#output\_this\_rds\_name) | The name of the RDS instance. |
<!-- END_TF_DOCS -->

## 提交问题

如果在使用该 Terraform Module
的过程中有任何问题，可以直接创建一个 [Provider Issue](https://github.com/aliyun/terraform-provider-alicloud/issues/new)，我们将根据问题描述提供解决方案。

**注意:** 不建议在该 Module 仓库中直接提交 Issue。

## 作者

Created and maintained by Alibaba Cloud Terraform Team(terraform@alibabacloud.com).

## 许可

MIT Licensed. See LICENSE for full details.

## 参考

* [Terraform-Provider-Alicloud Github](https://github.com/aliyun/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs)
