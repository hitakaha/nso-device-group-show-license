# What's this package?
This is an NSO package to execute license commands to a device group.

# How to use?
Just clone the package and execute "packages reload"
After the reload, a new command is added under device-group.

```
admin@ncs# devices device-group xr ?
Possible completions:
  check-sync            Check if the NCS config is in sync with the device
  check-yang-modules    Check if NCS and the devices have compatible YANG modules
  clear-trace           Clear all trace files
  connect               Set up sessions to all unlocked devices
  disconnect            Close all sessions to the devices
  fetch-ssh-host-keys   Retrieve SSH host keys from all devices
  ned-id                This list contains the ned-ids set on the devices included in this device group
  scp-to                Secure copy file to multiple devices
  show                  Execute show commands to a device-group        <<<< new command
  sync-from             Synchronize the config by pulling from the devices
  sync-to               Synchronize the config by pushing to the devices
```

# Sample outputs
```
admin@ncs# show devices device-group xr       
devices device-group xr
 member [ xr-1 xr-2 ]

admin@ncs# devices device-group xr show license 
result 
=== xr-1 ===
Account Information:
  Smart Account: <none>
  Virtual Account: <none>

=== xr-2 ===
Account Information:
  Smart Account: <none>
  Virtual Account: <none>

admin@ncs# 

admin@ncs# show devices device-group asr1k     
devices device-group asr1k
 member [ asr1k-1 asr1k-2 ]

admin@ncs# devices device-group asr1k show license 
result 
=== asr1k-1 ===
Smart Licensing Status: UNREGISTERED/No Licenses in Use

=== asr1k-2 ===
Smart Licensing Status: UNREGISTERED/No Licenses in Use

admin@ncs# 
```


# Supported OS
Currently, IOS-XR and IOS-XE are supported.


