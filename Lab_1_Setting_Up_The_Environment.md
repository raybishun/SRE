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

### Create Rule to Open FW Completely
1 https://console.cloud.google.com/
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


### Adding the FW Rule to the VM



## Connect to a VM on GCP.


## Install Docker on Linux VM.


## Verify Git is installed.