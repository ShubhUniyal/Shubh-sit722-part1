# Cloud-Native DevOps Project (Part 1 of 5)

## Background

Our University Library is a cornerstone of academic resources, aims to enhance accessibility to educational materials through an advanced online platform. You has been asked to develop a cloud-native microservices architecture to support the library's diverse user base and streamline deployment processes. This project is divided into 5 parts as follows:

<style type="text/css">
  .highlight {
    background-color: black;
  }
</style>

<table>
    <tr>
        <th>No.</th>
        <th>Title</th>
        <th>Task</th>
    </tr>
    <tr class="highlight">
        <td>1</td><td>Deploying Microservice with PostgreSQL on Render</td><td>Task 4.2P</td>
    </tr>
    <tr>
        <td>2</td><td>Containerizing Microservices with Docker and Deploying to Local Kubernetes</td><td>Task 6.2P</td>
    </tr>
    <tr>
        <td>3</td><td>Containerizing Microservices with Docker and Deploying to Azure Managed Kubernetes</td><td>Task 7.2P</td>
    </tr>
    <tr>
        <td>4</td><td> Infrastructure as Code with Terraform</td><td>Task 8.2C</td>
    </tr>
    <tr>
        <td>5</td><td>CI/CD with Github Actions using Terraform</td><td>Task 9.2D</td>
    </tr>
</table>

By end of this project, you will gain a comprehensive understanding of essential DevOps practices and cloud-native application deployment techniques. More specifically, you will be able to do following:

1. Create Dockerfiles to containerize application and define the runtime environment.
2. Develop Kubernetes YAML files (deployment.yaml and service.yaml) to deploy and manage their microservice on Azure managed Kubernetes cluster.
3. Write Terraform scripts (main.tf, variables.tf, outputs.tf, provider.tf) to provision Azure infrastructure.
4. Deploy Azure Kubernetes Service (AKS) and integrate PostgreSQL for data storage.
5. Configure GitHub Actions workflows to automate the CI/CD pipeline.
6. Apply theoretical knowledge to real-world scenarios, enhancing their understanding of cloud computing and DevOps principles.

## Task
In this part of the project, you will integrate PostgreSQL to persist book data, enhancing the existing microservice. PostgreSQL offers robust relational database capabilities suitable for managing structured data, which aligns well with the needs of a book management system. You will create Postgres database on Render and deploy microservice.

### Steps

1. Downlaod code from the __Task Resources__ and unzip.
2. Create a github repository named : `<your-name-sit722-part1>`.
3. Add given code to a github repository (local first then push to the remote repo).
4. Create account on [Render](http://render.com/) using GitHub if you dont have one yet.
5. Create PostgreSQL database instance on [Render](http://render.com/).
6. Once database is created, copy the __External Database URL__ in notepad for future use.
7. Create new `WebService` and Deploy your microservice on [Render](http://render.com/) with following settings:
   * Name: <STUDENT_ID>_SIT722_PART1
   * Root Directory: `app`
   * Build Command: `pip install -r requirements.txt`
   * Start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`
   * Set Environment Variable:
     * DATABASE_URL: Your __POSTGRES DATABASE EXTERNAL URL__ which you have in notepad.
8. Once it is deployed, open `<RENDER_URL>/docs` url in browser. Check different endpoints via Swagger Docs such as `create new book`, `get all book`, and `delete book`.