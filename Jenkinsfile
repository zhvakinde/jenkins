pipeline {
    agent any
    stages {
        stage("clone"){
            steps{
                git branch: 'main', credentialsId: 'github', url: 'git@github.com:zhvakinde/jenkins.git'
            }
        }
        stage("tag"){
            steps{
                sh "git tag v0.1"
            }
        }
        }
  
  
