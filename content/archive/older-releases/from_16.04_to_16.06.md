# Upgrade to ejabberd 16.06

One data type must be changed on the users table. This can be done at any
time while ejabberd 16.04 is running. If you run an older version of ejabberd
you must follow database upgrade process for 16.03 and 16.04 first.

Note: this applies only to MySQL. Other backend does not need upgrade.

## MySQL database upgrade
``` bash
mysql -h host -u user database -p << EOF
ALTER TABLE muc_room MODIFY opts mediumtext NOT NULL;
EOF
```
