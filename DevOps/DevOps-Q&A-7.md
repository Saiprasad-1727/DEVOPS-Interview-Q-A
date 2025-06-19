## 1.  How do you create a jenkins job to build a maven project from a github repo ?

**Answer**

 - **step 1:** Open jenkins and click on "new item"
 - **step 2:** Enter a name for the job and select "Freestyle project", Then click "OK".
 - **Step 3:** In the "SOurce code management" Section, select "Git" and enter the repo url.
 - **step 4:** In the "build Triggers" section, choose "Github Hook trigger for thr GITScm pullling."
 - **Step 5"** In the "Build" section, click "add build step" and select "invoke top-level maven targets."
 - **step 6:** In the "Goals" Field, enter `clean install`.
 - **Step 7:** Save the job and click "Build Now" to test it.

## 2 .  Write a Script to automate the deployment of a Docker container for a simple wed application.

**Answer**

```bash
#!/bin/bash
 
# variables
IMAGE_NAME="Mywebapp"
CONTAINER_NAME="mywebapp_container"
PORT=8080

#Build Docker iamge
docker build -t $IMAGE_NAME .


# stop and remove any existing container

docker stop $CONTAINER_NAME && docker rm $CONTAINER_NAME


#run the docker container
docker run -d -p $PORT:80 --name $CONTAINER_NAME $IMAGE_NAME
```


## 3. How would you create and configure an S3 bucket using AWS CLT for storing application logs ? 

**ANSWER**

 - **step 1:** Create the bucket

    ```bash
    aws s3 mb s3://my-app-logs
    ```

 - **Step 2:** Apply a bucket policy to allow public read access (if needed)
 
```bash 
aws s3api put-bucket-policy --bucket my-app-logs --policy file://policy. json :
```   

 - **Step 3:** enable versioning on the bucket

```bash
  aws s3api put-bucket-versioning --bucket my-app-logs --versioning-configuretion Statuss=Enabled
```

 - **Step 4:** Enable server-side encryption

```bash
aws s3api put-bucket-encryption --bucket my-app-logs --server-side-encryption-configuration '{"Rules":[{"ApplyServerSideEncryptionByDefault":{"SSEAlgorithm":"AES256"}}]}'
```


## 4. Write an ansible playbook to install NGINX on a remote server.

**Answer**

```yaml
---
    - name: Install NGINX
      hosts: webservers
      become: yes
      tasks:
        - name: Update apt cache
          apt:
            update_cache: yes
        - name: Install NGINX
          apt:
            name: nginx
            state: present
        - name: Ensure NGINX is running
          service:
            name: nginx
            state: started
            enabled: yes
```            


## 5 . how would you set uo prometheus to monitor a kubernetes cluster ?

**Answer**

- 1 : create a namespace for monitoring

```bash
kubectl create namespace monitoring
```

- 2 : use helm to install prometheus

``bash
helm install prometheus stable/prometheus --name monitoring
```
- 3 : verify the installation

```bash
kubectl get pods -n monitoring
```

- 4 access the prometheus dashboard
```bash
kubectl port-forward -n monitoring deploy/prometheus-server 9090
```
Open `http://localhost:9090` in a browser.


## 6. Write a script to back up a MySQL database and store the backup in an S# bucket

**ANSWER**

```bash
#!/bin/bash

# Variables
DB_NAME="mydatabase"
DB_USER="mysuer"
DB_PASS="mypassword"
BACKUP_NAME="backup_$(date +%F).sql"
S3_BUCKER="s3:??mydatabase-backups"

#create backup
mysqldump -u $DB_USER -p$DB_PASS $DB_NAME > /tmp/$BACKUP_NAME

#upload to s3
aws s3 cp /tmp/$BACKUP_NAME $S3_BUCKET

# remove local backup
rm /tmp/$BACKUP_NAME
```
