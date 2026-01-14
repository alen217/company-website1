pipeline{
  agent any

  stages{
    stage('Stop old container'){
      steps{
        bat 'docker rm -f company-website1 || exit 0'
      }
    }
    stage('Checkout code'){
      steps{
        echo 'Pulling code from github'
        checkout scm
      }
    }
    stage('Building Docker Image'){
      steps{
        echo 'Building docker Image'
        bat 'docker build -t company=website1 .'
      }
    }
    stage('Run docker container'){
      steps{
        echo 'Running docker container'
        bat 'docker run -d -p 8070:80 company-website1'
      }
    }
  }
}
