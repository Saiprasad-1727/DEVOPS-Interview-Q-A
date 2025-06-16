## 1. Handling Deployment Failures 

**Question:** How do you handle a deployment failure? 

**Answer:** 

When a deployment fails, my first step is to review the logs and error messages to identify the root cause. I check for common issues such as misconfigurations, network problems, or code errors. If the issue is identified quickly, I resolve it and redeploy. If not, T roll back to the previous stable version to minimize downtime. Afterward, I perform a thorough root cause analysis and update our deployment process or scripts to prevent similar issues in the future.

## 2. Addressing Performance Issues

**Question:** How do you address performance issues reported in a production environment?

**Answer:** 

To address performance issues, I start by monitoring system metrics using tools
like Prometheus and Grafana to identify any anomalies. I also review application logs and 
traces to pinpoint performance bottlenecks. Common solutions include optimizing code, 
scaling resources, adjusting load balancers, and tuning databases. If necessary, I work
with the development team to implement fixes and continuously monitor the system to ensure
the issue is resolved. 


## 3. Resolving Configuration Management Issues 

**Question:** How do you resolve configuration drift in your infrastructure? 

**Answer:** 

To resolve configuration drift, I use configuration management tools like
Ansible, Puppet, or Chef to enforce desired state configurations. T regularly run
configuration checks and audits to detect drifts. When a drift is detected, I investigate
the cause and reapply the correct configuration using our management tool. Additionally, I
ensure that all changes go through version control and are deployed consistently across all
environments.

## 4. Database Connectivity Problems 

**Question:** How do you troubleshoot database connectivity issues?

**Answer:** 

To troubleshoot database connectivity issues, I first check network
connectivity between the application and the database server. I verify that the database 
service is running and check for any firewall or security group rules that might be
blocking access. I also review database logs for any errors or warnings. Ensuring correct 
configuration settings in the application and database connection strings is crucial. If 
needed.  i use database client tools to test connectivity directly.
