# Setting up the Lab

## Deliverables
* Create a Google Cloud Platform (GCP) account.
* Configure a VM on GPC.
* Connect to a VM on GCP.
* Install Docker on Linux VM.
* Verify Git is installed.

## Create a Google Cloud Platform (GCP) account.
1. Create a GCP account at: https://cloud.google.com/
2. Access the GCP Console: https://console.cloud.google.com/ (or click the Console link in the upper-right corner.)

## Configure a VM on GPC.
1. Create a new project, i.e.: CI-CD.
2. More Products
3. Compute Engine
4. VM instances
5. Create Instance
6. Choose a region, i.e. us-east4-c
7. Name: ci
8. Series: e2-medium (2 vCPU, 4GB RAM)
9. Book disk
10. OS: Ubuntu 20.04 LTS, x86/64, 20GB
11. Create
12. Firewall
13. Create
14. SSH

## Create Rule to Open FW Completely
1. https://console.cloud.google.com/
2. VPC network
3. Firewall
4. Create Firewall Rule
5. Name: open
6. Logs: Off
7. Network: default
8. Priority: 1000
9. Direction of traffic: Ingress
10. Action to match: Allow
11. Target tags: open
12. Source filter: IPv4 ranges
13. Source IPv8 ranges: 0.0.0.0/0
14. Protocols and ports: Allow all
15. Create

## Applying the FW Rule to the VM
1. Compute Engine
2. VM instances
3. Select the VM, ci
4. Edit
5. Networking
6. Network tags: open (that is what we tagged our firewall rule earlier.)
7. Save

## Verify FW Rule was Applied
1. VPC Network
2. Firewall
3. Click on the open firewall rule
4. Scroll down to Applicable to Instances
5. Find the ci VM listed.

## Installing and Verifying Docker on our Linux VM
```
sudo apt-get remove docker docker-engine docker.io containerd runc
sudo apt-get update
sudo apt-get install \
	ca-certificates \
	curl \
	gnupg \
	lsb-release

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor
-o /etc/apt/keyrings/docker.gpg

echo \
"deb [arch=$(dpkg --print-architecture)
signed-by=/etc/apt/keyrings/docker.gpg]
https://download.docker.com/linux/ubuntu \

(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list >
/dev/null

sudo apt-get install docker-ce docker-ce-cli containerd.io
docker-compose-plugin

sudo docker version
```

## Docker Smoke Test
```
sudo docker run hello-world
```

## Verify Git is installed.
```
git version
```