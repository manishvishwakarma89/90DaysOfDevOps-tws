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
| Task                          | Command | Purpose                                       | Expected Result                                     |
| ----------------------------- | ------- | --------------------------------------------- | --------------------------------------------------- |
| **Check Block Devices**       | `lsblk` | Lists all disks, partitions, and mount points | Shows devices like `/dev/nvme1n1`, `/dev/sda`, etc. |
| **Check Physical Volumes**    | `pvs`   | Displays existing LVM physical volumes        | Shows PV name, VG name, size                        |
| **Check Volume Groups**       | `vgs`   | Displays existing volume groups               | Shows VG name, size, free space                     |
| **Check Logical Volumes**     | `lvs`   | Displays logical volumes inside VGs           | Shows LV name, VG name, size                        |
| **Check Mounted Filesystems** | `df -h` | Shows mounted storage usage                   | Displays filesystem size, used space                |



### Task 2: Create Physical Volume
| Command                 | Purpose                                 | Output                       |
| ----------------------- | --------------------------------------- | ---------------------------- |
| `pvcreate /dev/nvme1n1` | Initializes disk as LVM Physical Volume | PV created successfully      |
| `pvs`                   | Verify PV creation                      | Shows `/dev/nvme1n1` in list |

### Task 3: Create Volume Group
| Command                           | Purpose                       | Output                      |
| --------------------------------- | ----------------------------- | --------------------------- |
| `vgcreate devops-vg /dev/nvme1n1` | Creates Volume Group using PV | VG created                  |
| `vgs`                             | Verify VG                     | Shows `devops-vg` with size |


### Task 4: Create Logical Volume
| Command                                  | Purpose                      | Output              |
| ---------------------------------------- | ---------------------------- | ------------------- |
| `lvcreate -L 500M -n app-data devops-vg` | Creates 500MB Logical Volume | LV created          |
| `lvs`                                    | Verify LV                    | Shows `app-data` LV |

### Task 5: Format and Mount Logical Volume
| Command                                       | Purpose                         | Output               |
| --------------------------------------------- | ------------------------------- | -------------------- |
| `mkfs.ext4 /dev/devops-vg/app-data`           | Formats LV with ext4 filesystem | Filesystem created   |
| `mkdir -p /mnt/app-data`                      | Creates mount directory         | Directory created    |
| `mount /dev/devops-vg/app-data /mnt/app-data` | Mounts logical volume           | Storage mounted      |
| `df -h /mnt/app-data`                         | Verify mount and size           | Shows ~500MB mounted |

