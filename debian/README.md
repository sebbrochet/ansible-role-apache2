Requirements

None.

Role Variables: 

Available variables are listed below, along with default values for tasks (see defaults/main.yml):

 - update_apache_conf: if you want to modify apache config file, default value True

 - apache_config_file: Set config file for apache , default value apache2.conf
 - deploy_path: set path directory for logs apache, web site directory
 - apache_server_name: set name file logs for logrotate template
 - apache_logrotate_rotation: set logrotation interval : daily, weekly , etc . Default value daily
 - apache_logrotate_count: set count for log files are rotated count times before being removed or mailed to the address specified in a mail directive. If count is 0, old versions are removed rather than rotated. Default value: 30  
 
 - mpm_mode: Set mode prefork or worker

  	* IF mpm_mode=prefork
          
		StartServers: Sets the number of child server processes created on startup, default value 4
		MinSpareServers: Set the minimum number of many child processes keep while waiting for requests, default value 5.
		MaxSpareServers: Set the maximum number of many child processes keep while waiting for requests, default value 5.
		MaxClients: Sets the limit on maximum simultaneous requests that can be supported by the server, default value 150.
		ServerLimit: Increase ServerLimit to set MaxClients above 256, default value 150
		MaxRequestsPerChild: Sets the limit on the number of requests that an individual child server process will handle, default value 0 

  	* If mpm_mode=worker
	TODO 


None.

Example Playbook

- hosts: webservers
  roles:
    - { role: apache }
