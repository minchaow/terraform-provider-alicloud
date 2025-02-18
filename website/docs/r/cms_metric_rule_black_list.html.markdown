---
subcategory: "Cloud Monitor Service"
layout: "alicloud"
page_title: "Alicloud: alicloud_cms_metric_rule_black_list"
sidebar_current: "docs-alicloud-resource-cms-metric-rule-black-list"
description: |-
  Provides a Alicloud Cloud Monitor Service Metric Rule Black List resource.
---

# alicloud_cms_metric_rule_black_list

Provides a Cloud Monitor Service Metric Rule Black List resource.

For information about Cloud Monitor Service Metric Rule Black List and how to use it, see [What is Metric Rule Black List](https://www.alibabacloud.com/help/en/cloudmonitor/latest/describemetricruleblacklist).

-> **NOTE:** Available in v1.194.0+.

## Example Usage

Basic Usage

```terraform
resource "alicloud_cloud_monitor_service_metric_rule_black_list" "default" {
  instances = [
  "{\"instancceId\":\"i-bp1ew0zfkjblsuwx****\"}"]
  metrics {
    metric_name = "disk_utilization"
  }
  category                    = "ecs"
  enable_end_time             = 1640608200000
  namespace                   = "acs_ecs_dashboard"
  enable_start_time           = 1640237400000
  metric_rule_black_list_name = "henghai1342432432432"
}
```

## Argument Reference

The following arguments are supported:
* `category` - (Required) Cloud service classification. For example, Redis includes kvstore_standard, kvstore_sharding, and kvstore_splitrw.
* `effective_time` - (Computed,Optional) The effective time range of the alert blacklist policy.
* `enable_end_time` - (Computed,Optional) The start timestamp of the alert blacklist policy.Unit: milliseconds.
* `enable_start_time` - (Computed,Optional) The end timestamp of the alert blacklist policy.Unit: milliseconds.
* `instances` - (Required) The list of instances of cloud services specified in the alert blacklist policy.
* `is_enable` - (Computed,Optional) The status of the alert blacklist policy. Value:-true: enabled.-false: disabled.
* `metric_rule_black_list_name` - (Required) The name of the alert blacklist policy.
* `metrics` - (Computed,Optional) Monitoring metrics in the instance.See the following `Block Metrics`.
* `namespace` - (Required) The data namespace of the cloud service.
* `scope_type` - (Computed,Optional) The effective range of the alert blacklist policy. Value:-USER: The alert blacklist policy only takes effect in the current Alibaba cloud account.-GROUP: The alert blacklist policy takes effect in the specified application GROUP.
* `scope_value` - (Computed,Optional) Application Group ID list. The format is JSON Array.> This parameter is displayed only when 'ScopeType' is 'GROUP.

#### Block Metrics

The Metrics supports the following:
* `metric_name` - (Required) The name of the monitoring indicator.
* `resource` - (Computed,Optional) The extended dimension information of the instance. For example, '{"device":"C:"}' indicates that the blacklist policy is applied to all C disks under the ECS instance.



## Attributes Reference

The following attributes are exported:

* `id` - The ID of the blacklist policy.
* `metric_rule_black_list_id` - The ID of the blacklist policy.
* `create_time` - The timestamp for creating an alert blacklist policy.Unit: milliseconds.
* `update_time` - Modify the timestamp of the alert blacklist policy.Unit: milliseconds.

### Timeouts

The `timeouts` block allows you to specify [timeouts](https://www.terraform.io/docs/configuration-0-11/resources.html#timeouts) for certain actions:
* `create` - (Defaults to 5 mins) Used when create the Metric Rule Black List.
* `delete` - (Defaults to 1 mins) Used when delete the Metric Rule Black List.
* `update` - (Defaults to 5 mins) Used when update the Metric Rule Black List.

## Import

Cloud Monitor Service Metric Rule Black List can be imported using the id, e.g.

```shell
$terraform import alicloud_cms_metric_rule_black_list.example <id>
```