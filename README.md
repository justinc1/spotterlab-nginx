# Ansible Collection - spotterlab.nginx

Just a sample to demonstrate a problematic role.

Docs:
- https://ansible.readthedocs.io/projects/molecule/getting-started/
- https://ansible.readthedocs.io/projects/molecule/examples/podman/

# Usage


```
cd collections/ansible_collections/
mkdir spotterlab
git clone https://github.com/justinc1/spotterlab-nginx.git nginx
cd nginx

python3.12 -m venv .venv
.venv/bin/activate

pip install ansible-core molecule ansible-lint
pip install molecule-plugins molecule-plugins[podman]
# shell completion
. <(_MOLECULE_COMPLETE=bash_source molecule)
```

```
cd extensions

# check your molecule instances are created/destroyed
molecule create
podman ps
podman exec -it molecule-rocky9 systemctl status
molecule destroy
podman ps

# change code, then
molecule converge
molecule verify

# Everything works. Really?
molecule test
```

## Next

- Try also with ubi8/ubi-ini image
