# Create Empty VM

```bat
C:\Users\Administrator\Desktop\tf>terraform.exe init

Initializing provider plugins...
- Checking for available provider plugins on https://releases.hashicorp.com...
- Downloading plugin for provider "vsphere" (1.6.0)...

The following providers do not have any version constraints in configuration,
so the latest version was installed.

To prevent automatic upgrades to new major versions that may contain breaking
changes, it is recommended to add version = "..." constraints to the
corresponding provider blocks in configuration, with the constraint strings
suggested below.

* provider.vsphere: version = "~> 1.6"

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```

```bat
C:\Users\Administrator\Desktop\tf>terraform.exe plan -out poc_tf_create-empty-vm.plan
Refreshing Terraform state in-memory prior to plan...
The refreshed state will be used to calculate this plan, but will not be
persisted to local or remote state storage.

data.vsphere_datacenter.dc: Refreshing state...
data.vsphere_datastore.datastore: Refreshing state...
data.vsphere_resource_pool.pool: Refreshing state...
data.vsphere_network.network: Refreshing state...

------------------------------------------------------------------------

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  + vsphere_virtual_machine.vm
      id:                                        <computed>
      boot_retry_delay:                          "10000"
      change_version:                            <computed>
      cpu_limit:                                 "-1"
      cpu_share_count:                           <computed>
      cpu_share_level:                           "normal"
      datastore_id:                              "datastore-29"
      default_ip_address:                        <computed>
      disk.#:                                    "1"
      disk.0.attach:                             "false"
      disk.0.datastore_id:                       "<computed>"
      disk.0.device_address:                     <computed>
      disk.0.disk_mode:                          "persistent"
      disk.0.disk_sharing:                       "sharingNone"
      disk.0.eagerly_scrub:                      "false"
      disk.0.io_limit:                           "-1"
      disk.0.io_reservation:                     "0"
      disk.0.io_share_count:                     "0"
      disk.0.io_share_level:                     "normal"
      disk.0.keep_on_remove:                     "false"
      disk.0.key:                                "0"
      disk.0.label:                              "disk0"
      disk.0.path:                               <computed>
      disk.0.size:                               "20"
      disk.0.thin_provisioned:                   "true"
      disk.0.unit_number:                        "0"
      disk.0.uuid:                               <computed>
      disk.0.write_through:                      "false"
      ept_rvi_mode:                              "automatic"
      firmware:                                  "bios"
      force_power_off:                           "true"
      guest_id:                                  "other3xLinux64Guest"
      guest_ip_addresses.#:                      <computed>
      host_system_id:                            <computed>
      hv_mode:                                   "hvAuto"
      imported:                                  <computed>
      latency_sensitivity:                       "normal"
      memory:                                    "1024"
      memory_limit:                              "-1"
      memory_share_count:                        <computed>
      memory_share_level:                        "normal"
      migrate_wait_timeout:                      "30"
      moid:                                      <computed>
      name:                                      "terraform-test"
      network_interface.#:                       "1"
      network_interface.0.adapter_type:          "vmxnet3"
      network_interface.0.bandwidth_limit:       "-1"
      network_interface.0.bandwidth_reservation: "0"
      network_interface.0.bandwidth_share_count: <computed>
      network_interface.0.bandwidth_share_level: "normal"
      network_interface.0.device_address:        <computed>
      network_interface.0.key:                   <computed>
      network_interface.0.mac_address:           <computed>
      network_interface.0.network_id:            "network-44"
      num_cores_per_socket:                      "1"
      num_cpus:                                  "2"
      reboot_required:                           <computed>
      resource_pool_id:                          "resgroup-38"
      run_tools_scripts_after_power_on:          "true"
      run_tools_scripts_after_resume:            "true"
      run_tools_scripts_before_guest_shutdown:   "true"
      run_tools_scripts_before_guest_standby:    "true"
      scsi_controller_count:                     "1"
      scsi_type:                                 "pvscsi"
      shutdown_wait_timeout:                     "3"
      swap_placement_policy:                     "inherit"
      uuid:                                      <computed>
      vapp_transport.#:                          <computed>
      vmware_tools_status:                       <computed>
      vmx_path:                                  <computed>
      wait_for_guest_net_routable:               "true"
      wait_for_guest_net_timeout:                "5"


Plan: 1 to add, 0 to change, 0 to destroy.

------------------------------------------------------------------------

This plan was saved to: poc_tf_create-empty-vm.plan

To perform exactly these actions, run the following command to apply:
    terraform apply "poc_tf_create-empty-vm.plan"
```

```bat
C:\Users\Administrator\Desktop\tf>terraform apply "poc_tf_create-empty-vm.plan"
vsphere_virtual_machine.vm: Creating...
  boot_retry_delay:                          "" => "10000"
  change_version:                            "" => "<computed>"
  cpu_limit:                                 "" => "-1"
  cpu_share_count:                           "" => "<computed>"
  cpu_share_level:                           "" => "normal"
  datastore_id:                              "" => "datastore-29"
  default_ip_address:                        "" => "<computed>"
  disk.#:                                    "0" => "1"
  disk.0.attach:                             "" => "false"
  disk.0.datastore_id:                       "" => "<computed>"
  disk.0.device_address:                     "" => "<computed>"
  disk.0.disk_mode:                          "" => "persistent"
  disk.0.disk_sharing:                       "" => "sharingNone"
  disk.0.eagerly_scrub:                      "" => "false"
  disk.0.io_limit:                           "" => "-1"
  disk.0.io_reservation:                     "" => "0"
  disk.0.io_share_count:                     "" => "0"
  disk.0.io_share_level:                     "" => "normal"
  disk.0.keep_on_remove:                     "" => "false"
  disk.0.key:                                "" => "0"
  disk.0.label:                              "" => "disk0"
  disk.0.path:                               "" => "<computed>"
  disk.0.size:                               "" => "20"
  disk.0.thin_provisioned:                   "" => "true"
  disk.0.unit_number:                        "" => "0"
  disk.0.uuid:                               "" => "<computed>"
  disk.0.write_through:                      "" => "false"
  ept_rvi_mode:                              "" => "automatic"
  firmware:                                  "" => "bios"
  force_power_off:                           "" => "true"
  guest_id:                                  "" => "other3xLinux64Guest"
  guest_ip_addresses.#:                      "" => "<computed>"
  host_system_id:                            "" => "<computed>"
  hv_mode:                                   "" => "hvAuto"
  imported:                                  "" => "<computed>"
  latency_sensitivity:                       "" => "normal"
  memory:                                    "" => "1024"
  memory_limit:                              "" => "-1"
  memory_share_count:                        "" => "<computed>"
  memory_share_level:                        "" => "normal"
  migrate_wait_timeout:                      "" => "30"
  moid:                                      "" => "<computed>"
  name:                                      "" => "terraform-test"
  network_interface.#:                       "0" => "1"
  network_interface.0.adapter_type:          "" => "vmxnet3"
  network_interface.0.bandwidth_limit:       "" => "-1"
  network_interface.0.bandwidth_reservation: "" => "0"
  network_interface.0.bandwidth_share_count: "" => "<computed>"
  network_interface.0.bandwidth_share_level: "" => "normal"
  network_interface.0.device_address:        "" => "<computed>"
  network_interface.0.key:                   "" => "<computed>"
  network_interface.0.mac_address:           "" => "<computed>"
  network_interface.0.network_id:            "" => "network-44"
  num_cores_per_socket:                      "" => "1"
  num_cpus:                                  "" => "2"
  reboot_required:                           "" => "<computed>"
  resource_pool_id:                          "" => "resgroup-38"
  run_tools_scripts_after_power_on:          "" => "true"
  run_tools_scripts_after_resume:            "" => "true"
  run_tools_scripts_before_guest_shutdown:   "" => "true"
  run_tools_scripts_before_guest_standby:    "" => "true"
  scsi_controller_count:                     "" => "1"
  scsi_type:                                 "" => "pvscsi"
  shutdown_wait_timeout:                     "" => "3"
  swap_placement_policy:                     "" => "inherit"
  uuid:                                      "" => "<computed>"
  vapp_transport.#:                          "" => "<computed>"
  vmware_tools_status:                       "" => "<computed>"
  vmx_path:                                  "" => "<computed>"
  wait_for_guest_net_routable:               "" => "true"
  wait_for_guest_net_timeout:                "" => "5"
vsphere_virtual_machine.vm: Still creating... (10s elapsed)
vsphere_virtual_machine.vm: Still creating... (20s elapsed)
vsphere_virtual_machine.vm: Still creating... (30s elapsed)
vsphere_virtual_machine.vm: Still creating... (40s elapsed)
```
