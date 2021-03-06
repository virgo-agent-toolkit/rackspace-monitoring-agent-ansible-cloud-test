Testing framework for agent2 on a cloud server (deb and rpm).

## Usage

Create a `servers` file within the root of this project in the following
format:

```
[rpm]
192.168.0.1

[deb]
192.168.0.2

[arch]
192.168.0.3

[arch:vars]
ansible_python_interpreter=/usr/bin/python2
```

Running the ansible-playbook will automatically:

1. Install the build tools needed for RPM and DEB based distros
2. Build the Agent2 binary
3. Build the RPM or DEB package

```sh
ansible-playbook  -u root site.yml -i servers -f 10 -l 192.168.0.1
```

