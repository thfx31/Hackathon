# Hackathon
# Security and Infrastructure Hardening  

## Step 1: Install and Configure Fail2ban  
- **Install Fail2ban**: Protect against brute-force attacks by banning IPs after multiple failed login attempts.  
- **Configure Jail File**: Define parameters like ban time, retry limits, and enable SSHD monitoring.  
- **Start Service**: Ensure Fail2ban service is running.  

---

## Step 2: Apply Sysctl Security Configurations  
- Harden system by applying kernel-level security configurations (e.g., disable ICMP broadcasts, source routing, and enable strict packet filtering).  
- Reload settings dynamically.  

---

## Step 3: Secure SSH Access  
- **Install OpenSSH Server**: Ensure SSH functionality is available.  
- **Backup Config**: Save a copy of the current `sshd_config` for rollback.  
- **Configure Parameters**: Customize SSH settings such as port, root login, allowed users, and connection limits.  
- **Set Permissions**: Secure SSH configuration file with appropriate ownership and permissions.  
- **Update Banner**: Add a custom MOTD (Message of the Day) for system access warnings.  
- **Restart SSH Service**: Apply the new configuration.  

---

## Step 4: Install and Configure UFW Firewall  
- **Install UFW**: Set up a firewall to manage traffic.  
- **Reset Rules**: Clear existing configurations for a clean start.  
- **Allow Specific Ports**: Open SSH and DNS ports for connectivity.  
- **Set Default Policies**: Reject incoming traffic and allow outgoing by default.  
- **Enable Firewall**: Activate UFW and reload rules.  

---

## Step 5: Install and Configure Docker  
- **Add GPG Key and Repository**: Integrate Docker’s official GPG key and repository.  
- **Update and Install**: Refresh repositories and install Docker packages.  
- **Start Service**: Ensure Docker is running and enabled on startup.  
- **Add User to Docker Group**: Grant non-root user access to Docker.  
- **Verify Installation**: Check and log the Docker version.  

---
