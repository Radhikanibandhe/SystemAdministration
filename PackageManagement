Package management is a method of installing and maintaining (which includes updating and probably removing as well) software on the system.

In the early days of Linux, programs were only distributed as source code, along with the required man pages, the necessary configuration files, 
and more. Nowadays, most Linux distributors use by default pre-built programs or sets of programs called packages, 
which are presented to users ready for installation on that distribution.

**Working of Package Management System**
                  If a certain package requires a certain resource such as a shared library, or another package, it is said to have a dependency. All modern package 
                  management systems provide some method of dependency resolution to ensure that when a package is installed, all of its dependencies are installed as well.
                  
In order to perform the task of package management effectively, we have two types of available utilities:

Low-level Package tool: 
                  These are tools which handle in the backend the actual installation, upgrade, and removal of package files

High-level Package tool:
                  These are tools which are in charge of ensuring that the tasks of dependency resolution and metadata searching -”data about the data”- are performed
                  
    DISTRIBUTION	          LOW-LEVEL TOOL	    HIGH-LEVEL TOOL
    
Debian and derivatives	       dpkg	               apt-get
       CentOS	                 rpm	                 yum
       
1. dpkg: It is a low-level package manager for Debian-based systems. It can install, remove, provide information about and build *.deb packages but it can’t automatically 
        download and install their corresponding dependencies.
        
2. apt-get: It is a high-level package manager for Debian and derivatives, and provides a simple way to retrieve and install packages, including dependency resolution, 
            from multiple sources using the command line. Unlike dpkg, apt-get does not work directly with *.deb files, but with the package proper name.
            
3. rpm: It is the package management system used by Linux Standard Base (LSB)-compliant distributions for low-level handling of packages. Just like dpkg, it can query,
        install, verify, upgrade, and remove packages, and is more frequently used by Fedora-based distributions, such as RHEL and CentOS.
        
4. yum: It adds the functionality of automatic updates and package management with dependency management to RPM-based systems. As a high-level tool, like apt-get or 
        aptitude, yum works with repositories.
        
***Working with yum***

            - YUM (Yellowdog Updater Modified) is an open source command-line as well as graphical based package management tool for RPM (RedHat Package Manager) based 
              Linux systems. It allows users and system administrator to easily install, update, remove or search software packages on a systems.
            
            - To install package with yum:
                  ex: $ yum install httpd 
                      (This installs Apache Web server on your system.)
                  If you want to install packages automatically without asking any confirmation, use option -y 
                  ex: $ yum -y install httpd
                      
            - To remove a package completely with their all dependencies:
                  ex: $ yum remove httpd
                      (This removes Apache Web Server with all its dependencies)
                  To disable confirmation prompt just add option -y
                  ex: $ tum -y remove httpd
                  
            - To update packages with yum:
                  ex: $ yum update httpd
                      (This updates Apache Web Server package)
                  
            - To get information of Package using yum;
                  ex: $ yum info httpd
                      (This gives all the information about Apache Web Server)
                      
            - To check for available updates:
                  ex: $ yum check-update
                  
            - To update System:
                  ex: $ yum update
                  
            - To view all the past transactions of yum command:
                  ex: $ yum history
                  
            - To undo a yum install:
                  ex: $ yum history undo
