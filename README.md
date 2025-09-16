# 🚀 Deploying Nginx Container using Jenkins
- This is an educational project demonstrating how to deploy an Nginx container using Jenkins. The pipeline automates the build and deployment process with Docker and Jenkins integrated with GitHub.

# 🛠️ Tools & Technologies Used
 - GitHub – Code repository
 - Jenkins – CI/CD tool
 - Docker – Containerization platform

## Ubuntu – OS platform used for setup
## 🧱 Project Structure
- Repo Structure in Github
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
- Do not use "https" , use "http"
  ``` bash
  http://<your-server-ip>:8081
## Default initial admin password:
- Change the password when you login to the jenkins
    ``` bash
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword

## 🐳 Step 2: Install Docker
- If you are using root you canavoid sudo
    ```  bash
    sudo apt update
    sudo apt install docker.io -y
    sudo systemctl start docker
    sudo systemctl enable docker
    sudo usermod -aG docker jenkins
    sudo usermod -aG docker $USER
    
- Note: Restart your system or log out/in after adding users to the Docker group.
  
## 🔌 Step 3: Install Required Jenkins Plugins
- Go to Manage Jenkins → Manage Plugins → Available Plugins and install the following:
- Docker Pipeline
- Pipeline
- Git

## 📁 Step 4: Create & Push Dockerfile to GitHub
- Example [\[Dockerfile\]](https://github.com/pra9jambare/JenkinsDeployContainer/blob/main/Dockerfile)

## 📄 Step 5: Create & Push index.html to GitHub
- Example [\[Index.html\]](https://github.com/pra9jambare/JenkinsDeployContainer/blob/main/index.html)

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
- Example [\[Jenkinsfile\]](https://github.com/pra9jambare/JenkinsDeployContainer/blob/main/Jenkinsfile)

## ▶️ Step 9: Run the Jenkins Pipeline
- Go to your pipeline project in Jenkins
- Click "Build Now"
- Monitor the console output for logs

## 🌐 Step 10: Access the Application
- Once the build is successful, access your Nginx app in the browser:
  ``` bash
  http://<your-server-ip>:8081
  
## 📚 Notes
- Ensure port 8081 is open in your firewall settings.
- Remove any existing containers with the same name before re-running.
- This setup is for educational purposes only; do not use in production as-is.

# Learn Together & Grow Together 
