# Ansible-Webserver

## Outline

- Build an Apache Web Server
- Deploy the weberver with the ansbile user
- Ansible user needs sudo
- Connection type ssh rather than paramiko
- Leave gathering of facts on

### - Info Needed:
  * - apache web server package name
  * - distribution running on
  * - apache version
  * - need the web server directory customized
  * - what is the site name

### - What needs to be done
  * - install the apache web server on the remote system(s)
  * - create the wev server directory
  * - web server directory has proper ownership
  #### - configuration of apache
    * - copy the http configuration file
    * - set up the vhost directory
    * - add any ssl keys if needed
    * - add the vhost template for the default site
  #### - copy the site code to the new directory
  #### - start the apache service
  ####- add/enable anyt modules needed
    * - mysql/mariadb
    * - ssl
    * - mod/rewrite
  #### - restart the apache service (or move the start to here)

### - Test
  - using lynx or telnet, test that the wev service is running
    - waitfor port 80 to be listening
  - register output for the service status as JSON on the completion of the playbook
