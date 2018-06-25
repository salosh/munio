Welcome to Munio
================

Goal
----------------

To become an easy entry point for cluster development

Features
----------------

 - Multisite management
 - Dynamic run-time variables
 - Easy network calculation


Deploy
----------------

Ansible 2.5.0 and above must be installed.

 * Clone and initialize Munio:
```shell                          
git clone https://github.com/salosh/munio.git
git config --global push.default matching
git config --global user.name "Your Name"
git config --global user.email your.email@salosh.org
cd munio
ansible-playbook playbooks/add_site.yml -i "127.0.0.1," -c local -e item_name=dev
```

 * Configure your environment:
```shell                          
nano sites/dev/hosts
```

 * Edit variables that are common to all sites:
```shell                          
nano sites/group_vars/foo_bar
```

 * Edit variables that are specific to the site you just created:
```shell
nano sites/dev/group_vars/all/90_sitevars
```

 * Deploy playbooks:
```shell                          
ansible-playbook -i sites/dev playbooks/name_of_playbook_here.yml
```

###### tags:
 - debug    # Show extra information about variables or data, for debugging
 - clear    # Clear/Delete/Remove previous artifacts, leftovers from old installations or OS defaults
 - init     # Initialize a component, (e.g create a default user for cluster management)
 - bin      # Install binaries / Extract archives for installation purposes
 - conf     # Deploy configuration items, templates, files
 - service  # Operate on services - restart/stop/disable
 - verify   # Verify functionality (e.g wait for a service port, make sure a file was created)
 - report   # Send metrics or verify results to an external monitoring system
 - xtraz    # Extra steps, not required for an operational site

* * *
Visit our website at https://munio.io
