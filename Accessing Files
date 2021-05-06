The concept of Linux File permission and ownership is crucial in Linux. Here is the explaination of Linux file permissions and ownership.

1. Ownership: 
              Every file and directory on your Unix/Linux system is assigned 3 types of owner, given below.
 
                 - User: A user is the owner of the file. By default, the person who created a file becomes its owner. 
                   Hence, a user is also sometimes called an owner.
 
                 - Group: A user- group can contain multiple users. All users belonging to a group will have the same 
                   Linux group permissions access to the file.
 
                 - Other: Any other user who has access to a file. This person has neither created the file, 
                   nor he belongs to a usergroup who could own the file. 

2. Permissions: 
              Every file and directory in your UNIX/Linux system has following 3 permissions defined for all the 3 owners discussed above.
              
                 - Read (4): This permission give you the authority to open and read a file. Read permission on a directory gives you the ability 
                    to lists its content.
                    
                 - Write (2): The write permission gives you the authority to modify the contents of a file. The write permission on a directory 
                    gives you the authority to add, remove and rename files stored in the directory.
                    
                 - Execute (1): In Unix/Linux, you cannot run a program unless the execute permission is set. If the execute permission is not set, 
                   you might still be able to see/modify the program code(provided read & write permissions are set), but not run it. 
                   
Setting Permissions:
                 - To change permissions of a file or directory , run a command
                      $ chmod [permission_code] filename
                      
                      permission-code:
                      4 - read permission
                      2 - write permission
                      1 - execure permission
                      
                      ex: $ chmod 755 file.txt 
                            Now file.txt has following permissions:
                              1. User: read / write / execute permissions (4 + 2 + 1 = 7)
                              2. Group: read / execute permissions (4 + 1 = 5)
                              3. Others: read / execute permissions (4 + 1 = 5)
                              
                  - To change the owner of the file, run following command:
                        $ chown username: groupname file.txt
