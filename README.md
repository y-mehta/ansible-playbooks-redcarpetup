## How to Use?

- Step 1: Add IP Addresses of master and worker nodes in the ```hosts``` file.
- Step 2: Configure master address and CIDR in ```variables``` file.
- Step 3: Run:  ansible-playbook configure_master_node.yaml
              ansible-playbook configure_worker_node.yaml


---

## Ansible Playbooks:

- Docker: ```playbooks/docker.yaml``` - Configure Docker on managed nodes.

- Kubernetes: 
  - ```playbooks/kube-config.yaml``` - For initial configurations and prerequisites.
  - ```playbooks/master-node.yaml``` - Initializes kubeadm, Create .kube directory in HOME, Copies kube config and Installs Pod Network on Master Node.
  - ```playbooks/worker-node.yaml``` - Get join token from master node and then use that token to join the cluster as a worker.

- Hardening:  
  - ```playbooks/cis_tests.yaml```   - Implemented few Controls/Recommendations from CIS Kubernetes Security Benchmark. Automatically fixes any misconfigurations found.
  - ```playbooks/cis_file_permissions.yaml``` - Contains re-usable function for testing file permissions and ownership.
  - ```playbooks/hardening.yaml```   - Installs & Configures firewalld, Installs fail2ban, Modified SSH Config to disallow Root Login and Login using Password.
            


## Todo:

- Implement all Kuberenetes CIS Benchmark Tests.
- Add more security hardening rules.



## Task Description:

At RedCarpet, we take security very seriously. The security/pentesting intern will also get "golden keys" - the main admin access to all our servers across India.
You will be expected to learn and contribute to devops (https://cloud.google.com/devops/) as well as site reliability engineering (https://landing.google.com/sre/).
 
So we expect you to learn tools and be a good devops coder as well. Remember, we know that you may not know how to do this. We are expecting you to learn and do the interview.
 
1. You will use Ansible to do server hardening. e.g. http://isa.com.gh/2018/05/how-to-automate-pentesting-with-ansible-part-1-installation-configuration/ or https://github.com/juju4/ansible-harden-windows/tree/master/tasks
2. Sign up for a free AWS/DigitalOcean/Vultr account. You will get free credits.
3. Create a linux Ubuntu server.
4. Do the following using ansible:
  4.1 Setup Docker
  4.1 Setup Kubernetes.
  4.3 Harden the server against attacks - you figure out what to do here. Use your security experience to secure the server.
 
Best of luck!
