OBSERVABILITY AND MONITORING 
- example autoscaling based on monioring and alerting rules (advanced)

OBSERVABILITY VIA GOLDEN SIGNALS (Google SRE handbook - https://sre.google/sre-book/table-of-contents/ )
- Latency - Time required to satisfy any request
- Traffic - How much demand for a given service eg.: http requests, throughput etc.
- Errors - Rate at which requests are failing, can be 200 ok as well.
- Saturation - Balance between system CPU, memory etc., vs utilisation - under utilised, over utilised, auto-scale

Why observability matters?
- Scale
- Reliability
- Resilience
- Availability
- Debugging
- ** Communication



**RANCHER DATADOG DEMO:**

Prerequisites:
1. Active AWS account with admin access
2. Access key and secret for an admin user in AWS
3. Signup for Datadog trial account
4. git - https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
5. helm >3.7.x - For Mac - `brew install helm`, For windows - `choco install kubernetes-helm`
(6. aws cli >2.x - https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
7. terraform - https://learn.hashicorp.com/tutorials/terraform/install-cli
8. kubectl - https://kubernetes.io/docs/tasks/tools/

Getting started:

**RANCHER (Kubernetes cluster)**

1. Clone https://github.com/shreeni123/devops-training-monitoring.git to local
2. `cd devops-training-monitoring/rancher/aws`
3. Rename terraform.tfvars.example to terraform.tfvars and fill in values for following variables with actual ones:

    `aws_access_key`
    
    `aws_secret_key`
    
    `rancher_server_admin_password = "admin"` (Line#15)

4. Save the file
5. `terraform init`
6. `terraform plan`
7. `terraform apply --auto-approve`
8. When provisioning has finished, terraform will output the URL to connect to the Rancher server
9. Login with url to rancher server

**DATADOG**
1. Signup for datadog trial, click on connect using docker, get the url eg : https://us3.datadoghq.com/ and the API key from the url
2. Using built in kubectl in rancher, run the commands:

`wget https://raw.githubusercontent.com/DataDog/helm-charts/main/charts/datadog/values.yaml`

`helm repo add datadog https://helm.datadoghq.com`

`helm repo update`

`helm install datadog-agent -f values.yaml --set datadog.apiKey=<API Key from DD account> --set datadog.dd_url=<your datadog site url eg.: https://us3.datadoghq.com/ > datadog/datadog --set targetSystem=linux`


** OBSERVING METRICS, DASHBOARDS - CONTAINER, PODS, DAEMONSETS MONITORING **
** SETTING UP BASIC ALERTS **

Further reading:
https://www.slideshare.net/OpsStack/how-to-monitoring-the-sre-golden-signals-ebook

** WINDING UP **


` terraform destroy`





