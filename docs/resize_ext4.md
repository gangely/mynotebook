resize ext4
===
## shrinking an ext4 partition
 1. resize to the *minimum* size
```
e2fsck -f /dev/<partn>
resize2fs -M /dev/<partn>
```
 2. expand the partition, as below
## expanding an ext4 partition
### re-create the partition with fdisk or gdisk:
  1. note the starting sector value of the target partition
  2. delete the target partition + possibly other in the required space
  3. re-create the target partition:
     * same partition number
     * starting sector: the **same** sector
     * ending sector: new value, larger than  size
### extend the partition to fill the new size
```
e2fsck -f /dev/<partn> 
resize2fs /dev/<partn>
```
