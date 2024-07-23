# EKS
Connecting to EKS running in the private subnet of AWS VPC from your DevBox.

## Architecture Diagram:

![image](../../../.gitbook/assets/eks-architecture.png)

## Existing EKS

### Step 1: Accessing EKS from a DevBox

1. Follow the [Connecting to AWS](../../existing-network/connecting-to-aws.md) guide.
2. Go to **Amazon Elastic Kubernetes Service > Clusters**.
3. Go to the **DevBox** and install awscli:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
sudo apt install awscli
```
{% endcode %}
4. Download the **kubectl** files:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
{% endcode %}
5. Install the **kubectl**:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
{% endcode %}
6. Check if the cluster is accessible:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
kubectl get svc
```
{% endcode %}

![image](../../../.gitbook/assets/eks-access.png)


## New EKS Machine

### Step 1: Creating an EKS Instance

1. Follow the [Connecting to AWS](../../existing-network/connecting-to-aws.md) guide.
2. Go to **Amazon Elastic Kubernetes Service > Clusters > Add cluster > Create**.
3. Enter name of the cluster and assign a **Cluster service role** that has **AmazonEKSClusterPolicy** permission. If no role is present, create a new one with the same permission.
4. Click on **Next**. In the **Networking** section, choose your VPC that the bastion host is running on and assign 2 private subnets . In the **Cluster endpoint access**, select **Private**.
5. Configure other settings as required and then create the cluster. After creating the cluster, go to the **compute** section and under **Node groups** click on **Add node group**.
6. Enter the name of the node group and assign a node IAM role with **AmazonEC2ContainerRegistryReadOnly**, **AmazonEKS_CNI_Policy** and **AmazonEKSWorkerNodePolicy** permission. If no role is present, create a new one with the same permissions.
7. Configure other settings as required and create the nodes.

![imgae](../../../.gitbook/assets/eks-cluster.png)

### Step 2: Installing necessary tools:

1. Go to the **DevBox** and install awscli:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
sudo apt install awscli
```
{% endcode %}
2. Download the **kubectl** files:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
{% endcode %}
3. Install the **kubectl**:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
{% endcode %}

### Step 3: Accessing the EKS Cluster:

1. Click on your AWS username at the top right corner and go to **Security credentials**. In the **Access keys** section, click on **Create access key**. Create the key and save the **CSV** file.
2. In your **DevBox**, use the csv credentials to configure the awscli to your account:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
aws configure
```
{% endcode %}
3. Check if the cluster is accessible:\
{% code overflow="wrap" lineNumbers="false" %}
```bash
kubectl get sev
```


![image](../../../.gitbook/assets/eks-access.png)
