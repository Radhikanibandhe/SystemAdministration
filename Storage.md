Storage in Linux:
The most common partitioning scheme for x 86 and x 86-64 computers has
gone by various names over the years, including master boot record (MBR),
MS-DOS, and BIOS partitioning . It supports three types of partitions

Primary: This is the simplest type of partition. A disk can have zero to four
         primary partitions, one of which may be an extended partition.
         
Extended: This is a special type of primary partition that serves as a placeholder
          for logical partitions. A disk may have at most one extended partition.
Logical: These partitions are contained within an extended partition. In theory,
a disk can have billions of logical partitions, thus overcoming the limit of
four primary partitions, but in practice you’re unlikely to see more than about a
dozen of them.

MBR’s use of three partition types is awkward and limiting, but inertia has
kept it in place for three decades. MBR partitions have a hard limit, though: they
can’t support disks larger than 2 tebibytes (TiB), assuming 512-byte sectors,
which are nearly universal today.

The Globally Unique Identifi er (GUID) Partition Table (GPT) is the successor
to MBR. GPT supports disks of up to 8 zebibytes (ZiB), which is about 4 billion
times as large as MBR’s limit. GPT also supports up to 128 partitions by default,
with no distinction between primary, extended, and logical partitions. In these
respects, GPT is a superior partitioning system to MBR; however, its support
varies between OSs. Linux supports both systems quite well. Windows can boot
only from MBR when the computer uses the Basic Input/Output System (BIOS),
and it can boot only from GPT when the computer is based on the Unifi ed
Extensible Firmware Interface (UEFI).

![image](https://user-images.githubusercontent.com/58497366/118368530-0fe5d180-b5c0-11eb-865e-5684aecf1c7b.png)


***Steps to Create Partition***
  1. List partitions
  
     $ parted -l
     
  2. Label a partition
  
     $ parted /dev/vdb mklabel msdos
      
  3. Use mkpart to make a partition
     
     (parted) mkpart 
     
     Partition type ? primary/extended ? primary 
     
     File System type ? [ext2]? xfs 
     
     Start ? 2048s 
     
     End ? 50% 
     
     (parted) print
   
  4. Let the partition be created/settled
  
     (parted) udevadm settle
     
  5. Attach the filesystem to the partition

     mkfs.xfs /dev/vdb1
     
  6. Create a mount point directory

     mkdir /archive
     
  7. Add entry in fstab
  
     cat /etc/fstab
     lsblk /dev/vdb
     lsblk --fs /dev/vdb
     vi /etc/fstab
     
     UUID = 8ac075e3-1124-4bb6-bef7-a6811bf8b870 / archive xfs defaults 0 0
     
  8. systemctl daemon-reload
  
  10. Mount partition on directory
  
      mount /archive
      
      df -h
     
  11. Reboot
     
     
