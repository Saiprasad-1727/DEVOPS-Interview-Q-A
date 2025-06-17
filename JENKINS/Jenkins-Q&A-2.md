## 1. what is a workspace in jenkins ?

*  In Jenkins, a workspace is the directory where Jenkins builds and stores files for a particular project. Each Job has its own workspace. For example, If you are ruming a
job to compile code, the source code and build artifacts will be stored in the workspace.

## 2. **if we want to take a backup of a post Jenkins server, what would be the process ?**

*  To backup a Jenkins server, you should backup the Jenkins home directory, which 
contains all the configurations, plugins, and job information. You can do this by:

```bash I
cp -r /var/1ib/Jenkins /path/to/backup/location 
```
* Automating this with a cron job and ensuring backups are stored securely is a good practise.

## 3. 
