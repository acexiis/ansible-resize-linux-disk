# Playbook to resize a Linux Redhat server disk and increase vCenter disk size if needed

## TODO:
  - Split playbook into 2 or 3 difffrents roles


## pre-requierement
  * Complet vars.yml if all your information (ex: vars_sample.yml).
  * Be sure to use the same network than your Server and vCenter server.
  * parted must be installed on your Linux server.

## playbook: resize_disk.yml

  ### play #1 (all): Resize vCenter disk for virtual machine        TAGS: [resize_on_vcenter]
> [!IMPORTANT]
> Use this playbook only if you do not have enough disk space available on your server.

      TASK TAGS: [resize_on_vcenter]
      
      * This playbook only increase the disk size on vCenter and do nothing on the Linux server
      


  ### play #2 (all): Resize The Disk on the machine TAGS: [increase_lvm_size]
      TASK TAGS: [add_new_partition, increase_lvm_size]]
      
      * You can use add_new_partition if you have just increased the disk size on vCenter.
        * This tags/block will be ignored if you have enough disk space available.
      * increase_lvm_size will increase the disk size using VGS space.
      
      