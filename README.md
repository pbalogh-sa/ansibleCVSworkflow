# ansibleCVSworkflow

This tool can commit and update specified file to CVS Repository.
Optional feature: run command after update

Examples:
- Run command after cvs update in nng group
  ```
  ansible-playbook --extra-vars "file=named.conf servers=nng destination=/etc/bind cvsdir=~/work/wcfg command='ls -all'" site.yml
  ```
- Only update remote files in barack, brian
```
  ansible-playbook --extra-vars "file=named.conf servers=barack;brian destination=/etc/bind cvsdir=~/work/wcfg" site.yml
```
Where:
  - file: filename on local (this will be copied to local CVS for commit and update on remote)
  - servers: server or group names
  - destination: directory on remote where we want to update the file
  - command: command with arguments

Test opportunities:
```
  --skip-tags "cvscommit,cvsupdate,cvslocalupdate"
```
