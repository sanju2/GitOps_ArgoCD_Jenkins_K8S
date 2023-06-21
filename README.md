## Jenkins pipeline with GitOps(ArgoCD) to deploy code into a Kubernete. 

- CI - Jenkins 
- CD - ArgoCD (GitOps)
- monitoring - Prometheus & Grafana

## Architectural Diagram
![ Architectural Diagram](Architecture-Diagram_GitOps_Project.png)

### [Manifest Repo](https://github.com/sanju2/manifest-repo)

> Used to follow the steps.

1. Create two repositories (buildimage, update manifest).

2. Install jenkins on EC2 and configure Jenkins. Install Gocker & Git on EC2.

Install the following plugins for the demo.
- Amazon EC2 plugin (No need to set up Configure Cloud after)
- Docker plugin  
- Docker Pipeline
- GitHub Integration Plugin
- Parameterized trigger Plugin

3. Create Jenkins 1 job - build image. Used this repository.

4. Create Jenkins 2 job - update manifest. Select update manifest repository.

5. Run build image job. You can see docker image is updated.

6. Create EKS Cluster and update .kubeconfig file.

7. Install argo cd using kubernetes and login console.

8. Create argo cd app and configure github hook.

9. Setup Prometheus & Grafana for Monitoring On Kubernetes Cluster.

> Screenshots

### EC2 Instance (Jenkins Server)
![Jenkins Server](screenshots/JenkinsServer.png)

### Build Jenkins job
![Jenkins Server 1](screenshots/Jenkins1.png)

### Manifest Update Jenkins job
![Jenkins Server 2](screenshots/Jenkins2.png)

### Jenkins Home Page
![Jenkins Server 3](screenshots/Jenkins3.png)

### ArgoCD Dashboard
![ArgoCD](screenshots/Argo-CD.png)

### Prometheus Dashboard
![Prometheus](screenshots/prometheus.png)

### Grafana Dashboard
![Grafana](screenshots/Grafana.png)

### Final Output
![Output](screenshots/Final_Output.png)

## Resources

[Jenkins Install on AWS EC2](https://www.jenkins.io/doc/tutorials/tutorial-for-installing-jenkins-on-AWS)

[Docker install on EC2](https://serverfault.com/questions/836198/how-to-install-docker-on-aws-ec2-instance-with-ami-ce-ee-update)

[ArgoCD Install](https://argo-cd.readthedocs.io/en/stable/getting_started)

[Prometheus](https://devopscube.com/setup-prometheus-monitoring-on-kubernetes)

[Grafana](https://devopscube.com/setup-grafana-kubernetes)

### Thank You! :shipit: