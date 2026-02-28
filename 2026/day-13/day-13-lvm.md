## Day 13 – Linux Volume Management (LVM)
Task
Learn LVM to manage storage flexibly – create, extend, and mount volumes.

Watch First: Linux LVM Tutorial

Expected Output
A markdown file: day-13-lvm.md
Screenshots of command outputs

<hr>

### Commands Used
### Task 1: Check Current Storage
<ul>
<li> lsblk      # List all block devices and partitions
 </li>
<li> pvs        # Show existing physical volumes </li>
<li>vgs        # Show existing volume groups</li>
<li> lvs        # Show existing logical volumes </li>
<li> df -h      # Show mounted filesystems and their usage</li>


### Task 2: Create Physical Volume
<ul><li> pvcreate /dev/nvme1n1   # Initialize /dev/nvme1n1 as a physical volume for LVM </li>
<li> pvs                      # Verify physical volume creation </li>
</ul>

### Task 3: Create Volume Group
<ul>
<li> vgcreate devops-vg /dev/nvme1n1   # Create a volume group named devops-vg </li> 

<li> vgs                                # Verify volume group creation
</li>
</ul>

### Task 4: Create Logical Volume
<ul>
 lvcreate -L 500M -n app-data devops-vg   # Create a logical volume named app-data with 500MB
 lvs                                       # Verify logical volume creation
</ul>
### Task 5: Format and Mount Logical Volume
<ul>
 mkfs.ext4 /dev/devops-vg/app-data               # Format LV with ext4 filesystem
 mkdir -p /mnt/app-data                          # Create mount point
 mount /dev/devops-vg/app-data /mnt/app-data    # Mount LV
 df -h /mnt/app-data                             # Verify mounted filesystem size and usage
 
</ul>
