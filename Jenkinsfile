node {
        stage('Prepare environment') {
            
             git branch: 'main', url: 'https://github.com/zhvakinde/jenkins' 
             script {
             env.Commit = sh(script: 'git rev-parse HEAD', returnStdout: true)?.trim()
             env.TAG_NAME= sh(script: "git describe --tags ${Commit} --abbrev=0", returnStdout: true)
}
      

}
        stage('Deploy') 
          sshagent (credentials: ['nginx'])
        {

       sh "ssh -o StrictHostKeyChecking=no test@84.252.141.168 'mkdir -p /var/www/${env.TAG_NAME}'"
       sh "scp -o StrictHostKeyChecking=no index.html test@84.252.141.168:/var/www/${env.TAG_NAME}"
       sh "ssh -o StrictHostKeyChecking=no test@84.252.141.168 'unlink /var/www/web'"

       sh "ssh -o StrictHostKeyChecking=no test@84.252.141.168 \'ln -s /var/www/${env.TAG_NAME} /var/www/web\'"
   }
}

