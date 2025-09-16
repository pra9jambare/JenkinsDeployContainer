# 🚀 Deploying Nginx Container using Jenkins
- This is an educational project demonstrating how to deploy an Nginx container using Jenkins. The pipeline automates the build and deployment process with Docker and Jenkins integrated with GitHub.

# 🛠️ Tools & Technologies Used
 - GitHub – Code repository
 - Jenkins – CI/CD tool
 - Docker – Containerization platform

## Ubuntu – OS platform used for setup
## 🧱 Project Structure
    ```bash
    .
    ├── Dockerfile
    ├── index.html
    ├── Jenkinsfile
    └── README.md

## ✅ Prerequisites
- Make sure you're running this on an Ubuntu machine and have sudo/root access.

## 🔧 Setup Instructions
- 📌 Step 1: Install Jenkins
    ``` bash
    sudo apt update
    sudo apt install openjdk-11-jdk -y
    wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb https://pkg.jenkins.io/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt update
    sudo apt install jenkins -y
    sudo systemctl start jenkins
    sudo systemctl enable jenkins

## 📌 Access Jenkins at:
    <pre> ``` http://&lt;your-server-ip&gt;:8080 ``` </pre>
## Default initial admin password:
    ``` bash
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword

## 🐳 Step 2: Install Docker
    ``` bash
    sudo apt update
    sudo apt install docker.io -y
    sudo systemctl start docker
    sudo systemctl enable docker
    sudo usermod -aG docker jenkins
    sudo usermod -aG docker $USER
    
- Note: Restart your system or log out/in after adding users to the Docker group.
- 
## 🔌 Step 3: Install Required Jenkins Plugins
- Go to Manage Jenkins → Manage Plugins → Available Plugins and install the following:
- Docker Pipeline
- Pipeline
- Git

## 📁 Step 4: Create & Push Dockerfile to GitHub
- Example Dockerfile:-
  ``` bash
  FROM nginx:latest
  COPY index.html /usr/share/nginx/html/index.html

## 📄 Step 5: Create & Push index.html to GitHub
- Example index.html:
  ``` bash
  <!DOCTYPE html>
  <html>
  <head>
      <title>Welcome to Nginx!</title>
  </head>
  <body>
      <h1>Hello from Jenkins-deployed Nginx container!</h1>
  </body>
  </html>

## ⚙️ Step 6: Create a New Jenkins Pipeline
- Open Jenkins Dashboard
- Click on "New Item"
- Enter a name, select Pipeline, and click OK

## 🔗 Step 7: Connect Jenkins to GitHub
- In your Jenkins Pipeline configuration:
- Under Pipeline → Definition, choose Pipeline script from SCM
- SCM: Git
- Enter your GitHub repository URL
- Set branch (default: main or master)

## 📝 Step 8: Write & Push Jenkinsfile to GitHub
- Example Jenkinsfile:

