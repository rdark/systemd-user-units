# systemd-user-units

Misc systemd user units from my workstation 

# Units

## Checkmail@.service

Runs an [mbsync][mbsync_home] process for the given mbsync configuration stanza

[mbsync_home]: http://isync.sourceforge.net/

The service depends on the generic `network-online.target` If you use
NetworkManager to manage your connectivity, you can get this working with the
generic `network-online.target` by enabling
`NetworkManager-wait-online.service` which results in the desired behaviour of
only attempting to run mbsync when we have a routable network address.

### Usage

Enable the timer unit for a given instance(s):

    systemctl enable --user checkmail@username_at_domain.timer
    systemctl enable --user checkmail@username_at_other_domain.timer
