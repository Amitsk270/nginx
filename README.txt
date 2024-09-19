1.Ansible has to be installed in the system.
2.minikube setup should be ready to run the ansible playbooks.
3.install the below dependencies before running the ansible scripts.
ansible-galaxy collection install community.kubernetes
ansible-galaxy collection install community.general

sudo apt update
sudo apt install python3-pip

sudo apt install python3-venv   #download environment to run the k8s deployments..
python3 -m venv ~/myenv  # You can choose a different name or location if desired(Create a Virtual Environment)
source ~/myenv/bin/activate          #(Activate the Virtual Environment)
pip install kubernetes             #install
which python                #for python interpreter path for ansible playbook ,please replace the ansible playbook with correct path for variable python interpreter.(this has to be replaced in deployansible.yml and ingressansible.yml.)


4.sudo user for running the ansible script.
5.make sure the all the manifests are present before the ansible playbook.(deployment.yml,ingressroute.yml should be present.)

6.to deploy and ingress controller and ingress route please run the below ansible playbook.
ansible-playbook deployansible.yml
ansible-playbook ingressansible.yml

once the above 2 ansible are run ,we can test the output.
7.before testing the output please add the minikube ip in the /etc/hosts for resolve purpose.(we can get the minikube ip by running the command-minikube ip)
8.go to browser type amitskexample.com (we will be getting the expected output.)

10.to test the output with certificate please run the below ansible playbook.
ansible-playbook certificateansible.yml

11.now after going to browser and type amitskexample.com and we will be getting the expected output we with certificate.
