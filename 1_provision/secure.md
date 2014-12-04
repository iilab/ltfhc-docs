# Securing the Server

 - Change root server
 - Install unlock private keys on laptop (root / drc).
 - Generate key on laptop with user passphrase.
 - Install laptop public key on server.

# 

After the provisioning process the following is the case:
  - couchdb is in Admin Party

The security goals are:
 - Make the data encrypted at rest.
 - Prevent the data to be read unless an authorized laptop with an authorized password is present in the network.
 - Each laptop should have a unique key with a unique passphrase that is kept in the district office.
 - Avoid replay attacks for someone capturing packets on the wireless lan.
 - If someone compromises one installation (by coercing a user to give away their password for instance), it shouldn't compromise other instances.
 - It should allow other district users to have also a key to access the server.
 - It should allow a spare laptop to be provisioned only with master key from iilab/ltfhc. (i.e. the decrypted luksKeyfile is only kept by iilab/ltfhc)
 - [optional] check availability of specific file on mounted USB drive to launch boot during maintenance.

Security non-goals
 - Does not try to protect against someone with root access to the server
 - Does not try to protect against coercion against health care worker.
 - 

Description
 - The server will boot up completely but won't start the EMR application until it has received a keyfile from the laptop.
 - The master passphrase for the volume is never shared.

Laptop has login screen which uses the login / password to:
 1/ select the private key named "$user.key" and pipe the password as passphrase to decrypt luksKeyfile.
 2/ pipe decrypted luksKeyfile to https service.

Provisioning a new laptop / user
 - when provisioning the user should have a pgp private key created and the public key uploaded to the 
 - Encrypt a deployment luks key to the laptop's public key. 

    gpg --encrypt --recipient ltfhc@iilab.org --recipient kalemie@ltfhc.iilab.org --recipient $user@ltfhc.iilab.org luksKeyfile.key


# dd if=/dev/urandom of=/var/lib/ltfhc-data bs=1M count=500
# losetup /dev/loop0 /var/lib/ltfhc-data 
# cryptsetup luksFormat /dev/loop0
# cryptsetup luksOpen /dev/loop0 ltfhc-data
# mkfs.ext4 /dev/mapper/ltfhc-data
# systemctl stop ltfhc-couch.service
# mkdir /mnt/ltfhc-data
# mount /dev/mapper/ltfhc-data /mnt/ltfhc-data

# Then partition mounted with empty couchdb and master accounts created (root, deploy, jun)

# then 
# systemctl stop ltfhc-couch.service
# umount /mnt/ltfhc-data
# cryptsetup luksClose /dev/mapper/ltfhc-data
# losetup -d /dev/loop0

# Copy empty container to secure location for provisioning.

# Mounting the partition should be
# losetup /dev/loop0 /var/lib/ltfhc-data 
# cryptsetup luksOpen /dev/loop0 ltfhc-data
# mount /dev/mapper/ltfhc-data /mnt/ltfhc-data
