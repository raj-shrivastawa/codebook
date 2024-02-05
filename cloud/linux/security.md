### Some basic commands User and Groups
* To check the current user belongs to which group. `groups` 
* chroot
* Get entry from database file like passwd. `getent passwd raj` 
* To remove user from group. `gpasswd --delete user group` 
Example: `gpasswd --delete sfuser docker` 
* To add user to group. `usermod -a -G group user`

