# Azure DevOps Service tutorial
This guideline helps you know how to create a simple job to build and deploy an application to Azure k8s using [Azure DevOps Service](https://azure.microsoft.com/en-us/services/devops/).

# Target
Create a simple job including 3 steps:
1. Intergrate with a code repository (Github).
2. Use *maven* to build war/jar file.
3. Build *docker image* and push it to *Azure Container Registry*.
4. Deploy the image to your Kubernetes cluster.

![](p-p1.png)

# Step 1: Create a project for your team and connect to your repository on Github.
1. Access [Azure DevOps Service](https://azure.microsoft.com/en-us/services/devops/).
2. Click *Start free* to get to Azure DevOps Service dashboard.

![](p-p2.png)

3. Click *New project*. 

![](p-new-pj.png)

4. Format project name: "teamname-appname"

![](p-team-name.png)

5. Access to builds and start a new pipeline.

![](p-start-build.png)

6. Select *classic editor*.

![](p-classic.png)

7. Connect to your repository on Github.

![](p-github.png)

![](p-github2.png)

8. Select empty job template.

![](p-select-empty.png)

9. Fill agent secification.

![](p-agent-spec.png)

# Step 2: Build war/jar file by maven.

1. Click on (+) icon to add a new task.

![](p-agent-spec.png)

2. Select maven task type.

![](p-select-maven.png)

3. Fill maven build information.

![](p-fill-maven.png)


# Step 3: Build and push docker image.

1. Add new task for docker build. 

![](p-build-docker.png)

2. Fill docker build specification including selecting Azure Container Registry and fill image name.

![](p-fill-docker.png)

# Step 4: Deploy to your kubernetes cluster.

1. Add new task for kubenetes deployment. 

![](p-select-kube.png)

2. Fill kubenetes deployment specification including selecting cluster, namespace (default) and yaml file path. 

![](p-kube-spec.png)

# Step 5: Save and queue and Finish.

1. Save and queue.

![](p-save.png)

3. The job is running.

![](p-running.png)

4. Checking logs.

![](p-log.png)

# Done