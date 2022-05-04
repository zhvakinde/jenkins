pipeline {
    agent any
    stages {
        stage("git"){
            step{
                git branch: 'main', credentialsId: 'github', url: 'git@github.com:zhvakinde/jenkins.git'
            }
        }
    }
}
