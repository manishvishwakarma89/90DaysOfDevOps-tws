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
lsblk      # List all block devices and partitions
pvs        # Show existing physical volumes
vgs        # Show existing volume groups
lvs        # Show existing logical volumes
df -h      # Show mounted filesystems and their usage


### Task 2: Create Physical Volume
pvcreate /dev/nvme1n1   # Initialize /dev/nvme1n1 as a physical volume for LVM
pvs                      # Verify physical volume creation

### Task 3: Create Volume Group
vgcreate devops-vg /dev/nvme1n1   # Create a volume group named devops-vg
vgs                                # Verify volume group creation

