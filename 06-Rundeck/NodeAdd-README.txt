How to add nodes?
- Bring up worker1 
- SSH-KeyGen on master/rundeck 
- Add the Private Key to RunDeck -> Setting -> KeyStore -> Upload the key ( amitkey ) 
- ProjectSettings -> EditConfiguration -> DefaultNode Excuter & DefaultFile Copoer -> SSH Key Storage Path ( amitkey ) 
- ProjectSettings -> EditNodes ->  Source -> Add a New Node Source -> File -> 
  Format: resource.xml 
  Path: /var/lib/rundeck/var/resourceModelSourceCache/MyTestProject/resourcexml
  

# cat  /var/lib/rundeck/var/resourceModelSourceCache/MyTestProject/resourcexml 
<?xml version="1.0" encoding="UTF-8"?>
<project>
<node name="worker1"
  osFamily="unix"
  username="vagrant"
  hostname="172.31.0.101"
  ssh-authentication="privateKey"
  sudo-command-enabled="true"
  sudo-password-storage-path="keys/amitkey"
  />
</project>
#
