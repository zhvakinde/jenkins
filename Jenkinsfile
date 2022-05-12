pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo " tag ${env.GIT_TAG_NAME} ${env.GIT_TAG_MESSAGE}"
            }
        }
    }
}
