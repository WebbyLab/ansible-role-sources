sources
=========

Deploys your source code from git to your server

Role Variables
--------------
Defaults:

    sources_target_user: web-app
    sources_version: master
    sources_repo: ssh://git@myserver.com:22/projects/web-app.git
    sources_git_pem:  files/git.pem
    sources_target_dir: ~/web-app

sources_version - git branch/tag/commit 
sources_git_pem - path to private key to get access to your git repo through ssh. By default it fill search file "git.pem"

Example Playbook
----------------
    - hosts: servers
      roles:
         - role: webbylab.sources
           sources_repo: ssh://git@myserver.com:22/projects/web-app.git
           sources_git_pem:  files/git.pem


You can clone several repositories

    - hosts: servers
      roles:
         - role: webbylab.sources
           sources_repo: ssh://git@myserver.com:22/projects/web-app-client.git
           sources_git_pem:  files/git.pem

         - role: webbylab.sources
           sources_repo: ssh://git@myserver.com:22/projects/web-app-backend.git
           sources_git_pem:  files/git.pem
License
-------

MIT

Author Information
------------------

WebbyLab (http://webbylab.com)