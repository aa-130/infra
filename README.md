We're going to allow exactly one manual bootstrap step on a fresh machine (WSL/Ubuntu in this case):

```bash
sudo apt update
sudo apt install -y git python3 python3-pip
pip3 install ansible
```

After that:

```bash
git clone <infra>
cd infra

ansible-playbook ansible/playbooks/workstation.yml
ansible-playbook ansible/playbooks/k3d.yml

cd terraform
terraform init
terraform apply
```
