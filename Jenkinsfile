pipeline {
    agent any
    stages {
        stage('Example') {
            tag_git = ${env.GIT_TAG_NAME}
            steps {
                echo " tag ${tag_git} ${env.GIT_TAG_MESSAGE}"
            }
        }
    }
}
