# Provisioning

## Provisioning Network Setup

 * Provisioning Laptop (Ethernet )


 * Download provisioning environment (Vagrant virtual machine with Cobbler)

```
git clone https://github.com/iilab/ltfhc-provision.git
```

 * Start provisioning environment

```
cd ltfhc-provision
vagrant up
```

 * Check that provisioning environment web interface is working

Browse to ```http://192.168.168.100/cobbler_web```
Login with user ```cobbler``` and password ```cobbler```

 * 

 * Download configuration environment ansible 

```
git clone https://github.com/iilab/ltfhc-provision.git
```

 * Login via SSH once to add the machine's fingerprint to local known_hosts file

ssh lastmile@192.168.168.170

 * Run ansible provisioning

./run.sh
