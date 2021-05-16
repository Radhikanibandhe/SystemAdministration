Hard Links:
            - A hard link is duplicate directory entry. Each hard linked file is assigned the same inode (index code: stores the 
              attributes & disk block locations of object's data) value as the original, and threfore they reference to same physical location.
              
            - Hard links remain linked even if the original or linked files are moved throughout the filesystem.
            
            - Ths disadvantage of hard links is that it cannot be created for files on different filesystems and it cannot be created for special
              files or directories.
              
            - Command for creating a hard link:
                    $ ln file.txt hardlink.txt
                   
Soft Links:
            - A soft link is similar to shortcut feature in Windows operating system. Also known as Symbolic link.
            
            - Each soft linked file contains a seperate inode value that points to the original value. 
            
            - Soft link contains the path for original file and not contents.
            
            - Removing soft link doesn't affect anything but removing original file, the link becomes "Dangling" link.
            
            - A soft link can link to a directory.
            
            - Command to create a soft link:
                    $ ln -s file.txt softlink.txt
