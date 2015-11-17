# Apache Role
This role was written to install Apache with a sane default configuration,
and to configure any number of VHOSTs with default settings.

## Tasks
### On Debian-Based Systems
1. Install Apache2
2. Unlink ALL MPM modules
3. Copy apache2.conf
4. Create a SSL\_MUTEX directory
5. Copy module configuration files (for modules listed in apache\_modules\_config)
6. Enable the modules (via a2enmod) (for modules listed in apache\_modules)
7. Configure VHOSTs (for sites listed in apache\_vhosts)
8. Enable VHOSTs (for sites listed in apache\_vhosts)
9. Configure root VHOST directory
10. Configure subdirectories for VHOSTs (for sites listed in apache\_vhosts)
11. Copy ports.conf
12. Start Apache2 and configure it to run on startup

### On RedHat-Based Systems
1. Install HTTPD
2. Install Mod\_SSL
3. Copy httpd.conf
4. Copy ssl.conf
5. Create root VHOST configuration directory
6. Configure VHOSTs (for sites listed in apache\_vhosts)
7. Create root VHOST directory
8. Create subdirectories for VHOSTs (for sites listed in apache\_vhosts)
9. Copy ports.conf
10. Start HTTPD and configure it to run on startup

## Variables
The following variables should be set before using this role
- apache\_vhosts
  Array containing a list, which holds the name and an array of aliases for the site
  Example:
  `apache_vhosts: [
    {
      name: 'example.com',
      aliases: ['www.example.com']
    }
  ]`
