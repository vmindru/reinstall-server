reinstall-server
=========

Trigger server reinstall using a predefined kickstart and adding a simple
grub install entry.

Requirements
------------

none

Role Variables
--------------

    reinstall_ks_url: URL to your kickstart file 
    reinstall_vmlinuz_url: URL to your vmlinuz file
    reinsatll_initrd_url: URL to your initird file
    reinstall_grub_root: default disk to reinstall on 
    reinstall_grub_ks_url: variable used for a prompt during manual execution, used to avoid accidental reinstalls
    reinstall_additioanl_kernel_params: additioanl parameters to be passed to linux section of grub entry

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers

      vars_prompt:
      - name: "server_reinstall"
        prompt:  "Do you want to reinstall this server ? this will wipe
                  all your data on this server yes/no ?"
        default: "no"
        private: no
        confirm: yes

      roles:
         - { role: reinstall-server }

License
-------

GNU GPLv3


Author Information
------------------

vmindru@redhat.com 
mindruv@gmail.com
