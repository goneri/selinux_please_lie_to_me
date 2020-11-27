# SELinux: please lie to me! 😭

This package provides a fake `selinux` module. This mocked `selinux` module
will always pretend SELinux is not enabled on the system.

## But why? 😕

If your system runs SELinux and run Ansible in a virtualenv you will probably
face this error:

    Aborting, target uses selinux but python bindings (libselinux-python) aren't installed!

## Example

    $ virtualenv -p python3.6 venv
    $ source venv/bin/active
    $ pip install selinux_please_lie_to_me
    $ python3 -c 'import selinux; print(f"SELinux is enabled: {selinux.is_selinux_enabled()}, (which is probably a lie 🤫)")'
    SELinux is enabled: False, (which is probably a lie 🤫)
