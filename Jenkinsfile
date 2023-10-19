pipeline{
  agent any
  tools{
    maven 'maven'
    nodejs 'Nodejs'
  }
  stages{
    stage("Clean un"){
      steps{
        deleteDir()
      }
    }
    stage("Clone repo"){
      steps{
        sh "git clone https://github.com/MohamedAmineDev/devops-tp4.git "
      }
    }
    stage("Generate backend image"){
      steps{
        dir("devops-tp4/springboot/app"){
          sh "mvn clean install -DskipTests"
          sh "docker build -t web-backend ."
        }
      }
    }
    stage("Generate frontend image"){
      steps{
        dir("devops-tp4/angular-app"){
          sh "npm install"
          sh "docker build -t web-front ."
        }
      }
    }
    stage("Run docker compose"){
      steps{
        dir("devops-tp4"){
          sh "docker compose up -d"
        }
      }
    }
  }
}
