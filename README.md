
## DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout

https://www.youtube.com/watch?v=gLJdrXPn0ns 

https://raw.githubusercontent.com/RodrigoMvs123/DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/main/README.md

https://github.com/RodrigoMvs123/DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/blame/main/README.md
## What is DevSecOps ?

```
Main DevSecOps Concepts 
DevSecOps Tools
Hands-on experience 
```

Importance of Security

```
Application
Runtime
Infrastructure 
- On Premise
- Cloud Platform 
```

Challenges of implementing Security 
Focus on fast development of new features 

```
Application systems becomes more complex
Microservices
Containers
Kubernetes
Cloud 
Multiple Databases
External services
```

```
CICD Deploys to the Custer
Vulnerabilities on each layer 
Application
Own source code
Third party code
SQL injection
Cross-Site Scripting 
Client or Server Request Forgery 
Container Runtime
Image layer 
Docker image consist of multiple image layers
Docker image consist of your application code, but also underlying operating system, runtime, tools and packages, dependencies 
```

```
Container / Kubernetes Cluster
Cluster secured from outside 
Api server publicly accessible ?
Unneeded ports open ?
Access Management to cluster ?
Static long-term credentials or short-lived tokens ?
Security within the cluster?
Pod communication restricted ?
Access to Control Plane processes ?
Pod to Pod Encryption ?
```

```
Kubernetes / Cloud AWS
Cloud Infrastructure 
SSH into Worker Nodes directly ?
Is VPC wide open ?
```

```
Access Management 
Permissions not strict enough 
Credentials spread around the whole company 
Static credentials on engineer´s computer 
```

```
CI/CD Pipeline 
CI/CD is like an orchestrator, having access to many other systems 
Does your CI/CD tool have too many permissions ?
CI/CD access the cluster to make deployment updates 
Credentials stored in your CI/CD platform 
Private Repositories 
Kubernetes Cluster 
AWS Account 
All Platforms that connects to
Will the attacker get access to all credentials ?
What permissions do these credentials have ?
Restricted access ?
Admin access ?
Endless potential for security issues in different systems and technologies 
Secret management tools 
Credential rotations 
Certificates 
```

```
Security as Afterthought 
Developer/Engineer / Functional Tests / Build Image / Push to Repo / Deploy to Dev / Deploy to PROD 
Extensive Security Tests right before release 
Treated as a separate phase that occurs after the development is completed 
Long feedback cycles 
Slows down release pipeline
```

```
DevSecOps 
Incorporate security into development process and find security issues earlier 
Automated and frequent security checks 
```

```
What is DevSecOps ?
To deliver changes to the end user fast and with minimal bugs 
Applications Changes 
Infrastructure Changes 
In Practice 
DEV OPS 
Emphasizes collaboration between dev and ops teams to accelerate software delivery 
More focus on speed and efficiency in those areas 
SECURITY 
DevOps
Plan
Code
Build 
Test 
Release 
Deploy 
Operate 
Monitor 
Shared Responsibility
Everyone involved in the software development and delivery process shares responsibility for security 
Secure infrastructure 
Write secure application code 
Responsibility of fixing and implementing security still lies in individual teams, who have the expertise 
```

```
DevSecOps CI/CD
Pre-Commit Hook
Create Cache 
Secret Scanning - gitleaks / SAST - njsscan / SAST semgrep / SCA - retire.js / Functional Tests
Import Findings 
Build Image / Secure Push / Image Scanning - trivy / Continuous Scanning in Registry 
Secure Deploy Test
DAST - ZAP
Secure Deploy Prod
```

```
Automating 
security testing, vulnerability scanning, code analysis, compliance checks, …
Data
App
Host
Network
Physical 
Police and Procedures 
DevSecOps Concepts and Tools 
Automated tests for Application Security
Automated tests for Configuration Security
Automated tests for Cloud Security
```

```
SATS Tests ( Static Application Security Testing ) 
Static code analysis ( app is not running ) 
Identifies security vulnerabilities in app´s source code, configuration files, etc.
Look for common coding errors, deviation from secure coding practices etc.
Executing user input without validation
Passwords use outdated algorithms 
Validate our application code
SQL injection ?
Weak or outdated encryption algorithms ?
Cross-Site Scripting ?
```

```
Learn about different types of security attacks
SQL injection
XSS - Cross Site Scripting 
Client and Server Request Forgery 
Path Traversal 
Fix of those vulnerabilities 
See how it looks in practice 
```

```
Secret Scanning 
Tools that scan source code and detect hard-coded secrets
API Keys 
Password
Tokens 
Private Keys 
Authentication Files 
kubeconfig 
id_rsa
```

```
SCA Tests ( Software Composition Analysis ) 
Check third-party and open-source libraries and frameworks ( Dependencies of your application ) 
Third party code can have vulnerabilities, just like our own code
Packages Registry
NPM
Maven
Python
GO
Package imported / Dep ( Other people´s code ) / Own source code
SCA tool goes through our dependencies 
Dep ( Dependencies ) 
package vulnerability database
Checks if any known vulnerabilities for that dependency and specific version
List vulnerable dependencies 
SCA Section
Understand how it works in detail
How and where it's documented 
Learn about CVE´s 
How it works in practice 
Integrate SCA in DevSecOps pipeline
How to analyze the findings  
Impor SCA Scan reports 
How to fix it 
```

```
SAST / SCA / Secret Scanning 
All static analysis 
No need to run your application 
```

```
DAST Tests ( Dynamic Application Security Testing ) 
There are security issues that can only be detected when application is running
Focuses on identifying vulnerabilities in a running application 
No knowledge of the internal code or design of application 
SQL injection 
Manipulate URLs 
DAST tools probe an app from outside, just like a potential attacker would 
How does your app react to hacking attempts ?
```

```
Image Scanning 
Build Image 
Run 
Image 
Tools that validate the container image 
Scan every image layer for known vulnerability 
App Container 
Usage of ROOT user ?
Usage of vulnerable OS packages ?
Usage of bloated images ? 
```

```
Vulnerability Management 
Visualize and analyze the scan results 
How to generate reports of each scanning tool
Automatically upload findings with Python in CI/CD
Analyze findings and remediate security issues 
Understanding CWEs and CVE´s 
How it should work VS How it's done in practice
How to balance the additional security checks that increase the pipeline duration ?
When to run separate nightly builds or full scans ? 
```

```
Shifting Security to the Left 
Pre-Commit Hook
DEV / STAGING / PROD ( Release Pipeline ) 
Fast feedback on security issues 
 https://www.chef.io/ 
```

```

Application Security
Cloud Security 
Kubernetes Security 
Police as Code
Observability 
Compliance as Code
GitOps 
```

```
DevSecOps Demo
Vulnerable demo project 
```

```

OWASP open-source project
Python Web Application
Intentionally Vulnerable 
Security scanning tools are often specific to the tech stack of the app
```


## Github Repository 
https://github.com/adeyosemanputra/pygoat 

https://github.com/nanuchi/devsecops-crash-course-pygoat 

```
We will build a DevSecOps pipeline for that app ( Using GitHub Actions as a CI platform )
CI Pipeline with security checks 
Pushing new code changes 
Python/Git
SAST Scan 
Build Image 
Image Scanning 
```

```
Workflow Templates
```

```
Github UI
Github Actions Tab 
Workflow Continuous Integration
Pylint 
A workflow is a configurable automated process 
Workflow are defined in .github/workflow directory in a repository
Github will detect the pipeline code and run the defined jobs 
```

## Create CI Workflow 
SAST Scan
```
on: push = Triggers pipeline when a push is made to any branch in the repository 
on: [push, …] = You can specify multiple trigger events when using bracket 
jobs = Groups together all the jobs that run in the “CI” workflow
Bandit
Tool to find common security issues in Python code
Install tools you need 
Check out application code
Each job is executed on a fresh new environment 
Hosted by GitHub or self-hosted option 
```

Edit: 

DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -r .
```

Commit changes…

```
Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
create main.yml 
```

SAST Scan Result 

```
create main.yml 
main.yml 
on: push 
Run Bandit Scan
Run Bandit Scan
```

```
Severity Level
Refers to the degree of impact or potential harm a security vulnerability could have
Often categorized into
Critical or High
Medium 
Low or Warming 
Informational 
```

```
Helps us understand the level of risk and determine how urgently a security issue needs to be addressed 
```

```
Tweak tool for useful scanning findings 
Configure security tools and regularly review to
Focus on high severity vulnerabilities 
Mitigate false positives 
```

```
Confidence Level 
Refers to the degree of certainty or trust a security tool has the accuracy of a reported vulnerability 
```

```
Bandit´s severity and confidence categorization is based on OWASP´s risk rating 
```

```
Ignore Low Severity Issues 
```

Bandit Documentation
```
https://bandit.readthedocs.io/en/1.6.0/man/bandit.html?highlight=bandit-html#synopsis 
```

Edit 
```
run: bandit -ll -ii -r .
```
```
DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml
```

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -ll -ii -r .
```

Commit changes…

```
Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
Updated main.yml 
main.yml 
on: push 
Run Bandit Scan
Run Bandit Scan
High 
Medium 
```

Generate Scan Report 


```
Generating and consuming report files
Bandit / JSON / Report File
Report file generated by security scanning tool
File is meant to be consumed by other tools 
```

Bandit Documentation
```
https://bandit.readthedocs.io/en/1.6.0/man/bandit.html?highlight=bandit-html#synopsis 
```

Edit 

 run: bandit -ll -ii -r . -f json -o bandit-report.json
```
    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: bandit-findings 
        path: bandit-report.json
```

Edit: 
```
DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml
```

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -ll -ii -r . -f json -o bandit-report.json

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: bandit-findings 
        path: bandit-report.json
```

Commit changes…

```
Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
Updated main.yml 
main.yml 
on: push 
Run Bandit Scan
Run Bandit Scan
```

```
Artifacts 
Produced during runtime 
Name
bandit-findings 
Download
bandit.report.json 
```

```
Container Image Scanning 
Bandit 
Python
Scan security issues in application code 
```

```
CI/CD 
Docker Image 
We produce Docker images as application artifacts 
Image Layer 
Docker images consist of multiple image layers
Each layer could have a security vulnerability 
Each command in Dockerfile creates an image layer 
Base images consist of a Dockerfile with it own image layers 
```

```
Docker Image Scan 
docker scout 
https://docs.docker.com/scout/ 
Docker Scout is a set of software supply chain features integrated into Docker´s user interfaces and CLI 
Provides insights into the composition and security of container images 
```

```
Next Steps: 
SAST Scan / Build Image / Image Scan 
```

Github UI
```
Marketplace 

setup-docker 
uses: docker-practice/actions-setup-docker@v1
```

```
Docker Scout
docker scout quickview 
Display a quick overview of an image
Gives you base image refresh and update recommendations
docker scout cves 
Analyzes a software artifact for vulnerabilities 
Display CVE´s identified in a software artifact 
```

Edit:
```
image_scan: 
  name: Build Image and Run Image Scan 
  runs-on: ubuntu-latest

  steps: 
   - name: Checkout code
     uses: actions/checkout@v2
     
   - name: Set up Docker
     uses: docker-practice/actions-setup-docker@v1
     with: docker_version: '20.10.7' 

   - name: Build Docker Image
     run: docker build -f Dockerfile -t myapp:latest .

   -  name: Docker Scout Scan
      run: |
      curl -fsSL https://raw.githubusercontent.com/docker/scout-cli/main/intall.sh -o install-scout.sh
      sh install-scout.sh
      docker scout quickview
      docker scout cves
```

Edit:
```
DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml
```

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -ll -ii -r . -f json -o bandit-report.json

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: bandit-findings 
        path: bandit-report.json
        
image_scan: 
     name: Build Image and Run Image Scan 
     runs-on: ubuntu-latest

  steps: 
   - name: Checkout code
     uses: actions/checkout@v2
     
   - name: Set up Docker
     uses: docker-practice/actions-setup-docker@v1
     with: docker_version: '20.10.7' 

   - name: Build Docker Image
     run: docker build -f Dockerfile -t myapp:latest .

   - name: Docker Scout Scan
     run: |
       curl -fsSL https://raw.githubusercontent.com/docker/scout-cli/main/intall.sh -o install-scout.sh
       sh install-scout.sh
       docker scout quickview
       docker scout cves
```

Commit changes…

```
Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
Updated main.yml 
main.yml 
on: push 
Run Bandit Scan
Build Image and Run Image Scan
Build Docker Image 
```

Github
```dockerfile
FROM python:3.11.0b1-buster

# set work directory
WORKDIR /app


# dependencies for psycopg2
RUN apt-get update && apt-get install --no-install-recommends -y dnsutils=1:9.11.5.P4+dfsg-5.1+deb10u9 libpq-dev=11.16-0+deb10u1 python3-dev=3.7.3-1 \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*


# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1


# Install dependencies
RUN python -m pip install --no-cache-dir pip==22.0.4
COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt


# copy project
COPY . /app/


# install pygoat
EXPOSE 8000


RUN python3 /app/manage.py migrate
WORKDIR /app/pygoat/
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "--workers","6", "pygoat.wsgi"]
```

```
CI/CD 
Push to Docker Registry 
Deploy to AWS Environment 
Connect to platforms with Credentials
```

```
USERNAME DB_USER
projects secrets and variables 
Github UI
Settings
Secrets and variables 
```

Log IN on Docker UI ( rodrigomvs123 )

```
Actions Secrets and variables 
New repository secret 
Actions secret / New secret 
Name 
REPO_USER 
Secret
rodrigomvs123
Add secret 
Name
REPO_PWD
Secret
( Docker Password ) 
Add secret 
```

Edit:
```
echo ${{ secrets.REPO_PWD }} | docker login -u ${{secrets.REPO_USER}} --password-stdin
```

Edit:
```
DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml
```

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -ll -ii -r . -f json -o bandit-report.json

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: bandit-findings 
        path: bandit-report.json
        
image_scan: 
  name: Build Image and Run Image Scan 
  runs-on: ubuntu-latest

  steps: 
   - name: Checkout code
     uses: actions/checkout@v2
     
   - name: Set up Docker
     uses: docker-practice/actions-setup-docker@v1
     with: docker_version: '20.10.7' 

   - name: Build Docker Image
     run: docker build -f Dockerfile -t myapp:latest .

   - name: Docker Scout Scan
     run: |
       curl -fsSL https://raw.githubusercontent.com/docker/scout-cli/main/intall.sh -o install-scout.sh
       sh install-scout.sh

       echo ${{ secrets.REPO_PWD }} | docker login -u ${{secrets.REPO_USER}} --password-stdin
       
       docker scout quickview
       docker scout cves
```

Commit changes…

Scan Results 

```
Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
Updated main.yml 
main.yml 
on: push 
Run Bandit Scan
Build Image and Run Image Scan
Build Docker Image 
Docker Scout Scan
```

```
docker scout recommendations 
Displays available base image updates and remediation recommendation
For each recommendation it shows a list of benefits, such as fewer vulnerabilities or smaller image size 
```

Reuse existing action

```
Github UI
Marketplace 
Docker Scout 
```

Edit: 
```
name: Docker Scout Scan
      uses: docker/scout-action@v1.0.9
      with:
        dockerhub-user: ${{secrets.REPO_USER}}
        dockerhub-password: ${{ secrets.REPO_PWD }}
        command: quickview,cves 
```

Edit:
```
DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml
```

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -ll -ii -r . -f json -o bandit-report.json

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: bandit-findings 
        path: bandit-report.json
        
image_scan: 
  name: Build Image and Run Image Scan 
  runs-on: ubuntu-latest

  steps: 
   - name: Checkout code
     uses: actions/checkout@v2
     
   - name: Set up Docker
     uses: docker-practice/actions-setup-docker@v1
     with: docker_version: '20.10.7' 

   - name: Build Docker Image
     run: docker build -f Dockerfile -t myapp:latest .

  # - name: Docker Scout Scan
   #  run: |
    #   curl -fsSL https://raw.githubusercontent.com/docker/scout-cli/main/intall.sh -o install-scout.sh
     #  sh install-scout.sh

      # echo ${{ secrets.REPO_PWD }} | docker login -u ${{secrets.REPO_USER}} --password-stdin
       
      # docker scout quickview
      # docker scout cves

    - name: Docker Scout Scan
      uses: docker/scout-action@v1.0.9
      with:
        dockerhub-user: ${{secrets.REPO_USER}}
        dockerhub-password: ${{ secrets.REPO_PWD }}
        command: quickview,cves 
```

Commit changes…

```
Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
Updated main.yml 
main.yml 
on: push 
Run Bandit Scan
Build Image and Run Image Scan
Build Docker Image 
Docker Scout Scan

Github UI
Marketplace 
Docker Scout 
```

## Github Repository
https://github.com/docker/scout-action 


Only Critical and High Level Vulnerabilities 


Edit: 
```
 only-severities: critical,high 
        sarif-file: scout-report.sarif 

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: docker-scout-findings 
        path: scout-report.sarif
```

Edit:
```
DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml
```

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -ll -ii -r . -f json -o bandit-report.json

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: bandit-findings 
        path: bandit-report.json
        
image_scan: 
  name: Build Image and Run Image Scan 
  runs-on: ubuntu-latest

  steps: 
   - name: Checkout code
     uses: actions/checkout@v2
     
   - name: Set up Docker
     uses: docker-practice/actions-setup-docker@v1
     with: docker_version: '20.10.7' 

   - name: Build Docker Image
     run: docker build -f Dockerfile -t myapp:latest .

  # - name: Docker Scout Scan
   #  run: |
    #   curl -fsSL https://raw.githubusercontent.com/docker/scout-cli/main/intall.sh -o install-scout.sh
     #  sh install-scout.sh

      # echo ${{ secrets.REPO_PWD }} | docker login -u ${{secrets.REPO_USER}} --password-stdin
       
      # docker scout quickview
      # docker scout cves

    - name: Docker Scout Scan
      uses: docker/scout-action@v1.0.9
      with:
        dockerhub-user: ${{secrets.REPO_USER}}
        dockerhub-password: ${{ secrets.REPO_PWD }}
        command: quickview,cves 
        only-severities: critical,high 
        sarif-file: scout-report.sarif 

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: docker-scout-findings 
        path: scout-report.sarif
```

Commit changes…


```
Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
Updated main.yml 
main.yml 
on: push 
Run Bandit Scan
Build Image and Run Image Scan
```

Edit
```
exit-code: true
```

Edit:
```
DevSecOps-Tutorial-CI-Pipeline-with-GitHub-Actions-and-Docker-Scout/.github/workflows
/main.yml
```

```
name: CI 

on: [push]

jobs: 
  sast_scan: 
    name: Run Bandit Scan
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2 

    - name: Set uo Python
      uses: actions/setup-python@v2 
      with:
        python-version: 3.8 

    - name: Install Bandit 
      run: pip install bandit 

    - name: Run Bandit Scan 
      run: bandit -ll -ii -r . -f json -o bandit-report.json

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: bandit-findings 
        path: bandit-report.json
        
image_scan: 
  name: Build Image and Run Image Scan 
  runs-on: ubuntu-latest

  steps: 
   - name: Checkout code
     uses: actions/checkout@v2
     
   - name: Set up Docker
     uses: docker-practice/actions-setup-docker@v1
     with: docker_version: '20.10.7' 

   - name: Build Docker Image
     run: docker build -f Dockerfile -t myapp:latest .

  # - name: Docker Scout Scan
   #  run: |
    #   curl -fsSL https://raw.githubusercontent.com/docker/scout-cli/main/intall.sh -o install-scout.sh
     #  sh install-scout.sh

      # echo ${{ secrets.REPO_PWD }} | docker login -u ${{secrets.REPO_USER}} --password-stdin
       
      # docker scout quickview
      # docker scout cves

    - name: Docker Scout Scan
      uses: docker/scout-action@v1.0.9
      with:
        dockerhub-user: ${{secrets.REPO_USER}}
        dockerhub-password: ${{ secrets.REPO_PWD }}
        command: quickview,cves 
        only-severities: critical,high 
        sarif-file: scout-report.sarif 
        exit-code: true 

    - name: Upload Artifact 
      uses: actions/upload-artifact@v3 
      if: always() 
      with:
        name: docker-scout-findings 
        path: scout-report.sarif
```

Commit changes…

```

Github Actions Tab 
All Workflows
Showing runs from all workflows
1 workflow run
Updated main.yml 
main.yml 
on: push 
Run Bandit Scan
Build Image and Run Image Scan
Docker Scout Scan 
```

Learn a Vulnerability Management Tool

Defect Jojo

https://www.defectdojo.org/ 

Automate Importing of Reports 

https://cwe.mitre.org/ 

```
Cloud and Kubernetes Security
Application Security
Cloud Security
Kubernetes Security
GitOps
Observability 
Compliance as Code
```

```
Cloud Security
Infrastructure Security
Server Administration 
Secure Deployment 
```
