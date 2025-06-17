## 1. **How can we chnage the permission for a file under Linux ?**

* To change the permissions of a file in Linux, use the `chmod` command. For example, if you have a file called `example.txt` and you went to give read and write permissions to others, you would use:

```bash
chmod 640 example.txt
```

## 2. **How can we list the partitions in linux ?**

* To list the partitions in linux, you can use the `lsblk` or `fdisk -l` commands, For instance:

```bash
lsblk
```
or

```bash
sudo fdisk -l
```
* this is useful when setting up a new disk or troubleshooting storage issues on your server.

## 3. **what is the command to find the current load average in the system ?**

* The `uptime` or `top` commands can be used to find the current load average:

```bash
uptime
```
or 

```bash
top
```

## 4. how to check all the running processes ?

* to check all the running processes, use the `ps` command with the `aux` options

```bash
ps -aux
```

or 

```bash
top
```

## 5. i want to give access to some instance, which is in a private subnet to a developer, how can we give access ?

* You can provide access to the instance using SSH with a bastion host or VPN. for
example, set up a bastion host in a public subnet that the developer can SSH into, and
from there, they can SSH into the private instance.

## 6. *Difference between private and public subnets?*

- **Public Subnets**: Has a route to the internet through an Tnternet Gateway. Resources
in a public subnet can directly access the internet

- **Private Subnets**: Does not have a direct route to the internet. Resources in a
private subnet typically sccess the internet through  NAT Gateways

* For instance, web servers are often placed in public subnets, while databases are 
placed in private subnets for security.

## 7. If i want to deny one IP address access to my infrastructure, how can i do thid in AWS?


* You can use security rows or network ACL. For exquple, to deny access using a security group:

- Go to the security group in the AS console.
- Add an inbound rule with the IP address to deny.
- set the action to deny.

* Using Network ACLs, you would add a deny rule for the specific IP address.

## 8. **What are the restrictions for Lambda service ?** 

    - Execution timeout: maximum 15 minnutes
    - memory allocation: Between 128MB to 10,240 MB
    - Disk space in /tmp: 512 MB
    - Environment variable: Maximum of 4 KB

* For instance, if you have a function that processes images, you need to ensure it completes within 15 minutes and uses less than the allocated memory.

## 9. I want to expose my app which is running in the EC2 instance to the outside, how can i do that ? 

* You need to:
 - Attach an Elastic TP to your EC2 instance.
 - Configure the security group to allow inbound traffic on the necessary ports (e.g. port 80 for HTTP).
 - Update your route tables to allow traffic to the instance.   

 ## 10. Difference between roles and policies ?

 - **Policies**: Documents that define permissions. They specify what actions are allowed or denied for which resources.
 - **Roles**: Entities that AS services or applications assume to obtain temporary security credentials. Roles have policies attached to define what actions they can perform

 * For example, you might have a policy that allows $3 access and attach it to a role. that an EC2 instance assumes.



