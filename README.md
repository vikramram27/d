## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_google"></a> [google](#requirement\_google) | ~> 5.11.0 |
| <a name="requirement_kubernetes"></a> [kubernetes](#requirement\_kubernetes) | ~> 2.25.2 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_google"></a> [google](#provider\_google) | 5.11.0 |
| <a name="provider_kubernetes"></a> [kubernetes](#provider\_kubernetes) | ~> 2.25.2 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [google_compute_address.nat](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_address) | resource |
| [google_compute_network.vpc_dsa_gke](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_network) | resource |
| [google_compute_router.dsa-router](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_router) | resource |
| [google_compute_router_nat.nat](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_router_nat) | resource |
| [google_compute_subnetwork.private](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_subnetwork) | resource |
| [google_container_cluster.primary](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/container_cluster) | resource |
| [google_container_node_pool.node_pools](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/container_node_pool) | resource |
| [google_project_service.compute](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/project_service) | resource |
| [google_project_service.container](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/project_service) | resource |
| [google_service_account.sa](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/service_account) | resource |
| [kubernetes_cluster_role_binding.dsa_sa](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/cluster_role_binding) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_cluster_name"></a> [cluster\_name](#input\_cluster\_name) | Cluster Name | `string` | n/a | yes |
| <a name="input_enable_logging"></a> [enable\_logging](#input\_enable\_logging) | enable logging for gke ? | `bool` | `true` | no |
| <a name="input_enable_monitoring"></a> [enable\_monitoring](#input\_enable\_monitoring) | enable monitoring for gke ? | `bool` | `true` | no |
| <a name="input_k8s-pods-ip-ranges"></a> [k8s-pods-ip-ranges](#input\_k8s-pods-ip-ranges) | range of internal ip address for pods | `string` | n/a | yes |
| <a name="input_k8s-service-ip-ranges"></a> [k8s-service-ip-ranges](#input\_k8s-service-ip-ranges) | range of internal ip address for service | `string` | n/a | yes |
| <a name="input_node_pools"></a> [node\_pools](#input\_node\_pools) | node pools configuration | <pre>map(object({<br>    node_count   = number<br>    machine_type = string<br>    disk_size_gb = number<br>  }))</pre> | n/a | yes |
| <a name="input_region"></a> [region](#input\_region) | Default Region for k8s cluster | `string` | n/a | yes |
| <a name="input_routing_mode"></a> [routing\_mode](#input\_routing\_mode) | The network-wide routing mode to use. If set to 'REGIONAL', this network's cloud routers will only advertise routes with subnetworks of this network in the same region as the router. If set to 'GLOBAL', this network's cloud routers will advertise routes with all subnetworks of this network, across regions. Possible values: ['REGIONAL', 'GLOBAL'] | `string` | `"REGIONAL"` | no |
| <a name="input_vpc_ip_cidr_ranges"></a> [vpc\_ip\_cidr\_ranges](#input\_vpc\_ip\_cidr\_ranges) | range of internal addresses that are owned by this subnetwork. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_gke-control-plane-endpoints"></a> [gke-control-plane-endpoints](#output\_gke-control-plane-endpoints) | Endpoint Gke cluster control plane |
