# Ansible Role: Nginx

- Master branch: [![Build Status](https://travis-ci.org/insspb/ansible-role-nginx.svg?branch=master)](https://travis-ci.org/insspb/ansible-role-nginx)
- Developer branch: [![Build Status](https://travis-ci.org/insspb/ansible-role-nginx.svg?branch=develop)](https://travis-ci.org/insspb/ansible-role-nginx)

## Description
This role will install and configure nginx web server on desired host.

## Requirements
No requiments yet.

## Role Variables
### Nginx config
Please refer to defaults/main.yml to see current supported configuration options.
### Sites config example
```yaml
nginx_sites:
    - site:
        name: "test.anovatio.fr"                                # Mandatory
        enabled: True                                           # If False will not be linked in sites-enabled folder
        do_not_create_dir: True                                 # When we use nginx as a proxy or load balancer we do not need to create directories in www folder.
        custom_config: True                                     # This is start point for our configuration. 
                                                                # Full custom configs allow us to make anything we want with nginx 
                                                                # outside ansible, but still check it as host state on ansible script run.
        custom_config_path: files/test.anovatio.fr              # This is path to config file if custom_config is true.

```
## Dependencies
Independent role.

## Example Playbook

```yaml
- hosts: all
  gather_facts: true
  roles:
    - insspb.nginx
```
## Development information

This role is developed with community help. 
Process of development follows this rule: 

 - You are free to add any pool request to develop branch. All request will be answered in timely manner. 
 - If you want to made any contribution, but do not know where to start - check issues.
 - Master branch updated just after significant changes in develop.
 - Please include documentation for new features. 
 - Please use variables.
 - Please do not forget to set defaults.
 - Please do your best to keep backward compatibility if possible.
 - Please use packet installation as default software installation method. Source installation must be optional anywhere if possible.
 - Please use official software developers repositories instead of general Debian/Ubuntu/Centos etc. 
 - Do you best to keep role independent from any other roles. User must have the way to choose what roles to use.

## License
MIT

## Author Information

This role is contributed and maintained by [Andrey Shpak](http://www.ashpak.ru). I am always available for [hire](https://www.upwork.com/o/profiles/users/_~01a780866aa29e4429/).