# Hackathon Mangoustes Project  

## Goal  
Set up a resilient infrastructure to host distributed applications web on a Docker Swarm cluster using two Raspberry Pi devices.  

---

## Step 1: Prepare Raspberry Pi Devices  
- Install Raspberry Pi OS Lite.  
- Assign unique hostnames and static IPs.  
- Enable SSH with user `mangoustes` (password: `Azerty77`).  

---

## Step 2: Install Docker and Docker Swarm  
- Install Docker on each device.  
- Initialize Swarm on Raspberry Pi 1 and join with others.  
- Create an attachable overlay network.  

---

## Step 3: Deploy Services  
- **Reverse Proxy**: Traefik for routing.  
- **Websites**: Nginx for two sites.  
- **Databases**: PostgreSQL & MySQL with replication for high availability.  

---

## Step 4: Monitoring  
- **Prometheus & Grafana**: Metrics collection and visualization.  
- **Node Exporter**: Monitor system resources.  

---

## Step 5: Security  
- Set up a Ansible.
   Launch with Ansible
- `fail2ban`
- `kernel`
- `sshd`
- `ufw`
- `docker`
 

---

## Step 6: Deploy Services Example  
Deploy a stack using `docker swarm` & `docker-compose.yml` , including Traefik, Nginx sites, PostgreSQL, Prometheus, and Grafana.  

---

## Step 7: Next Steps   
- Create documentation.    
- Optimize using metrics.  
