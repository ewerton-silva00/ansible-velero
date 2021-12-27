# Velero Disaster Recovery - Ansible Role

This project is a [`Ansible Role`](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html) to deployment the [`velero`](https://velero.io/) on Kubernetes.

## Requirements

- A [`Kubernetes`](https://kubernetes.io/) up and running.
- The [`kubectl`](https://kubernetes.io/docs/tasks/tools/) binary installed.
- The [`Helm`](https://helm.sh/) binary installed.
- [`Python3`](https://www.python.org/) installed.
- [`Pip`](https://pypi.org/project/pip/) installed.

## How to use

Clone this repository.
```bash
git clone https://github.com/ewerton-silva00/ansible-velero
```

Initialize a [`Virtual Environment`](https://docs.python.org/3/library/venv.html).
```bash
python3 -m venv ansible-velero
```

Activate the virtual environment.
```bash
source ansible-velero/bin/activate
```

Access the `ansible-velero` directory and install dependencies.
```bash
cd ansible-velero
sudo pip3 install -r requirements.txt
```
Make sure that accessing the Kubernetes cluster via kubectl is OK.
```bash
kubectl cluster-info
```

Execute the Velero Role.
```bash
ansible-playbook \
  --inventory inventories/hosts.yml \
  velero.yml
```
> _Note_: if the variable `velero_binary_install` is `true` you need to pass `--ask-pass` and `--ask-become-pass`, because require `sudo` privilege.
