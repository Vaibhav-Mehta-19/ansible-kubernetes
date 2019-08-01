# ansible-kubernetes
Setting u kubernetes cluster with th help of ansible playbooks.

How to use this (Setup Instructions):

1. Make all of your servers ready including the master and the worker nodes and make sure that they are all connected with the same network.
2. Make an entry of your each hosts in /etc/hosts file for name resolution.
3. Internet connection must be enabled in all nodes, required packages will be downloaded from kubernetes official yum repository.
4. Clone this repository into your master node.
5. There is a file "hosts" available , Just make your entries of your all kubernetes nodes. 
6. Provide your server details in "env_variables" file.
7. Deploy the ssh key from master node to other nodes for password less authentication using >ssh-keygen. Copy the public key to all nodes including your master node and make sure you are able to login into any nodes without password.
8. Run "kubernetes_cluster_setup.yml" playbook to setup all nodes and kubernetes master configuration as >ansible-playbook kubernetes_cluster_setup.yml   
9. Run "join_workers_nodes.yml" playbook to join the worker nodes with kubernetes master node after setting up cluster as >ansible-playbook join_workers_nodes.yml
10. Verify the configuration from master node using >kubectl get nodes