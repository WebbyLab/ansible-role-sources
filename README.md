sources
=========

Deploys your source code from git to your server

Role Variables
--------------

    sources_target_user: web-app
    sources_version: master
    sources_repo: ssh://git@myserver.com:22/projects/web-app.git
    sources_git_pk_path:  ../../../files/git_pk

sources_version - git branch/tag/commit 
sources_git_pk_path - path to private key to get access to your git repo through ssh

Example Playbook
----------------
    - hosts: servers
      roles:
         - role: webbylab.sources
           sources_repo: ssh://git@myserver.com:22/projects/web-app.git
           sources_git_pk_path:  ../../../files/git_pk
           sources_version: prod


You can clone several repositories

    - hosts: servers
      roles:
         - role: webbylab.sources
           sources_repo: ssh://git@myserver.com:22/projects/web-app-client.git
           sources_git_pk_path:  ../../../files/git_pk

         - role: webbylab.sources
           sources_repo: ssh://git@myserver.com:22/projects/web-app-backend.git
           sources_git_pk_path:  ../../../files/git_pk
License
-------

MIT

Author Information
------------------

WebbyLab (http://webbylab.com)