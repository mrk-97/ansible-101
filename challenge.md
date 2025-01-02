# Load-Balanced Web Application Deployment Challenge

## Scenario
Your organization needs to deploy a high-availability web application stack across multiple servers. You'll need to configure web servers, set up a load balancer, implement monitoring, and ensure secure SSH access.

## Initial Environment
- 3 Ubuntu 22.04 servers (web-1, web-2, web-3)
- 1 HAProxy server (lb-1)
- All servers accessible via SSH with root privileges
- Base inventory file provided

## Challenge Objectives
1. Deploy and configure a load-balanced web application infrastructure
2. Implement secure SSH access
3. Set up basic monitoring
4. Use Ansible best practices for organization and reusability

## Tasks

### 1. Infrastructure Setup
- Create a structured Ansible project with the following organization:
```
project/
├── group_vars/
├── host_vars/
├── roles/
├── inventory/
├── site.yml
└── requirements.yml
```

### 2. Web Server Configuration
- Install and configure Nginx on web servers
- Deploy a sample web application (provided as a static HTML file)
- Configure Nginx to serve the application on port 8080
- Implement health check endpoint at /health
- Configure proper logging

### 3. Load Balancer Setup
- Install and configure HAProxy
- Configure backend pools for web servers
- Implement round-robin load balancing
- Enable HAProxy statistics page
- Configure SSL termination

### 4. Security Implementation
- Create and distribute SSH keys
- Configure SSH hardening:
  - Disable root login
  - Use key-based authentication only
  - Change default SSH port
- Set up basic firewall rules using UFW

### 5. Monitoring Setup
- Install and configure Node Exporter on all servers
- Configure basic system monitoring
- Set up log rotation

## Constraints and Requirements

### Code Organization
- Must use roles for different components
- Implement at least one custom module
- Use templates for configuration files
- Implement proper variable management

### Security Requirements
- No plaintext passwords in code
- Use Ansible Vault for sensitive data
- Implement proper file permissions

### Best Practices
- Use handlers for service management
- Implement proper error handling
- Include proper documentation
- Use tags for task organization

## Success Criteria

### Functionality
1. Web application accessible through load balancer
2. Health checks passing on all web servers
3. Load balancer properly distributing traffic
4. SSL working correctly
5. SSH hardening properly implemented

### Code Quality
1. Roles properly structured
2. Variables appropriately managed
3. Templates implemented correctly
4. Custom module functioning as expected

### Security
1. No sensitive data exposed
2. Proper SSH configuration
3. Firewall rules correctly implemented
4. SSL properly configured

### Monitoring
1. Node Exporter accessible on all servers
2. Log rotation functioning
3. HAProxy statistics available

## Verification Steps
1. Test web application access through load balancer
2. Verify SSL certificate validation
3. Test SSH access with new configuration
4. Verify load balancer distribution
5. Check monitoring endpoints
6. Validate log rotation

## Bonus Challenges
1. Implement blue-green deployment capability
2. Add configuration for backup web server
3. Implement automated SSL certificate renewal
4. Add custom error pages
5. Implement rate limiting

## Resources Provided
- Base inventory file
- Sample web application files
- Basic role structure
- Example variable files
