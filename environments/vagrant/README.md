# Vagrant role
For simple playbook tests that can be safely run against a virtual machine.

## Prerequisites
You need to have the following software installed to use the Vagrantfile without making any modifications to it.
- Vagrant
- Virtualbox

## Notes about using ssh
When you create a virtual machine using this particular Vagrantfile, the virtual machine creates host keys during the creation of the machine. When you ssh to the server the host keys are added to your **~/.ssh/known_hosts**. When you destroy the virtual machine and recreate it, the host keys will change. Now if you were to ssh to the recreated server you would receive an error message saying that sshing to the server failed because the host keys have changed. This is a security measure that in normal situation should never be ignored. You could be a victim of a man-in-the-middle attack.

As we known the reason for the host key change, you can remove the old host key from your known_hosts and try again. The other option is to ignore host key checks for that particular server. The hosts-file for vagrant includes
`ansible_ssh_common_args='-o StrictHostKeyChecking=no'` which should take care of this, but it is my understanding that this doesn't work well with some older versions of ansible.

You also have the option of disable StrictHostKeyCheckingin with your .ssh/config -file or with ansible.cfg.

## Small cheatsheet for vagrant
There are multiple great resources available for how to use Vagrant. But here's a few commands to get you started.

NOTE: Run these commands in the same folder where the Vagrantfile is located.
#### Create a virtual machine using vagrant
```vagrant up```

#### Stop the virtual machine that Vagrant has created
```vagrant halt```

#### Delete the virtual machine
```vagrant destroy```

#### ssh into the virtual machine
```vagrant ssh```
