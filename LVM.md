Logical volume manager (LVM) introduces an extra layer between the physical disks and the file system allowing file systems to be :
– resized and moved easily and online without requiring a system-wide outage.
– Using discontinuous space on disk
– meaningful names to volumes, rather than the usual cryptic device names.
– span multiple physical disks

LVM comprises of few conceptual layers such as physical volume, logical volume and file systems.

Physical Volume (PV)
Each Physical Volume can be a disk partition, whole disk, meta-device, or a loopback file. Use the command pvcreate to initialize storage for use by LVM. Initializing a block device as physical volume places a label at the start of the device.

Volume Group (VG)
A Volume Group gathers together a collection of Logical Volumes and Physical Volumes into one administrative unit. Volume group is divided into fixed size physical extents. The command vgcreate creates a new volume group using the block special device Physical Volume path previously configured for LVM with pvcreate.
– VGs are made up of PVs, which in turn are made up of physical extents (PEs). The size of PE can differe in different VGs and is defined at the time of creating VG.
– The default size of PE is 4MB, but you can change it to the value you want at the time of VG creation.
– Generally, larger the PE size, better the performance (though less granular control of LV).

Logical Volume (LV)
A Logical Volume is the conceptual equivalent of a disk partition in a non-LVM system. Logical volumes are block devices which are created from the physical extents present in the same volume group. You can use command lvcreate to create a logical volume in an existing volume group.

File system
File systems are built on top of logical volumes. The command mkfs can be used to create file system on top of a logical volume. Once the file system is created we can mount the logical volume as per our need.

**Steps:**


1.List partitions:
     Parted -l
     
2.Label a partition:
     parted / dev /vdb mklabel msdos 
     parted -l 
     
3.Use mkpart to make a partition:
      parted /dev /vdb
      mkpart
      primary
      xfs
      2048s
      x%
      flag set ->set 1
      LVM
      on
      p
      
4. Let the partition be created/settled:
      quit 
      pvcreate /dev/vdb1 /dev/vdc1 
      vgcreate servervg/dev/vdb1 /dev/vdc1
      vgdisplay
      
5. To display vg:
      vgdisplay
      
6. Attach the file system to the partition:
      mkfs. xFs /dev/servervg/serverlv
      
7. Create a mount point directory:
      df-h 
      mkdir / archive
      
8. Add entry in fstab:
      cat/etc/fstab
      vi/etc/fstab
      lsblk -- fs / dev / vdb
      
10. Systemctl daemon-reload

11. Mount the partition on the directory:
      mount/archieve
      df-h
