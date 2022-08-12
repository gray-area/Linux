# Update ESXi Server

To install the ESXi rollup update offline:

* Sign in to the VMware website (you can use a personal account) and go to https://my.vmware.com/group/vmware/patch;

* Select a product: ESXi (Embedded and Installable) and your ESXi build;


* The latest available update for offline install; download patch (update) for esxi from vmware website


* Download a ZIP file with the update (Offline);


* Use the Datastore Browser to copy the archive to any datastore available to your host


* Connect to your ESXi host via SSH and put the host in the maintenance mode: ``esxcli system maintenanceMode set --enable=true``


* To install the patch, run the command: 
``esxcli software vib update --depot /vmfs/volumes/VOLUMEWHEREUPDATESTORED/update/NAMEOFUPDATEPACKAGE.zip``


* Reboot your ESXi host: ``reboot -f``


* Disable the maintenance mode: ``esxcli system maintenanceMode set --enable=false``


* Make sure that the OS version has been updated: ``vmware –v``
