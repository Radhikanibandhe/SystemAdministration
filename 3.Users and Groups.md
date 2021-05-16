Linux is a multi-user system, which means that more than one person can interact with the same system at the same time. 
As a system administrator, you have the responsibility to manage the system’s users and groups by creating and removing users and assign them to different groups.

useradd:
        - In Linux, a ‘useradd' command is a low-level utility that is used for adding/creating user accounts in Linux and other Unix-like operating systems.
        
        - When we run ‘useradd‘ command in Linux terminal, it performs following major things:
            - It edits /etc/passwd, /etc/shadow, /etc/group and /etc/gshadow files for the newly created User account.
            - Creates and populate a home directory for the new user.
            - Sets permissions and ownerships to home directory.
            
        - Basic syntax of command is: 
            useradd [options] username
            
        - To add/create a new user, all you’ve to follow the command ‘useradd‘ or ‘adduser‘ with ‘username’. The ‘username’ is a user login name
          that is used by user to login into the system.
          ex: $ useradd username
          
        - When we add a new user in Linux with ‘useradd‘ command it gets created in locked state and to unlock that user account
          we need to set a password for that account with ‘passwd‘ command.
          ex: $ passwd username
          
        - Once a new user created, it’s entry automatically added to the ‘/etc/passwd‘ file. 
        
groupadd:
        - In Linux, groups are used to organize and administer user accounts. The primary purpose of groups is to define a set of privileges such as reading, writing, or 
          executing permission for a given resource that can be shared among the users within the group. The groupadd command creates such groups.
          
        - Basic syntax of command is:
            groupadd [options] groupname
            
        - Only the root or a user with sudo privileges can create new groups.
        
        - To create a new group named mygroup run a command
             $ groupadd mygroup     (The command adds an entry for the new group to the /etc/group and /etc/gshadow files.)
             
        - To create a group named mygroup with GID of 1010, run a command
             $ groupadd -g 1010 mygroup  
             
usermod: 
        - The command ‘usermod‘ is used to modify or change any attributes of a already created user account via command line.
        
        - When we execute ‘usermod‘ command in terminal, the following files are used and affected.
            - /etc/passwd – User account information.
            - /etc/shadow – Secure account information.
            - /etc/group – Group account information.
            - /etc/gshadow – Secure group account information.
            - /etc/login.defs – Shadow password suite configuration.
            
         - Basic syntax of command is;
             $ usermod [options] username
             
         - The basic requirements of this command are
            - We must have existing user accounts to execute usermod command.
            - Only superuser (root) is allowed to execute usermod command.
            
         - To add user to a group run the command: 
             $ usermod -aG groupname username   (a- append, G- secondary group)
             
***To switch users use command:  ***
      su - username
