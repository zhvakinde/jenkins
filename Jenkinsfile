node {

    String gitTagName() {
    commit = getCommit()
    if (commit) {
        return sh(script: "git describe --tags ${commit} --abbrev=0", returnStdout: true)?.trim()
    }
    return null
}

 String getCommit() {
    return sh(script: 'git rev-parse HEAD', returnStdout: true)?.trim()
}
     
     stage('Build') { 
        withEnv(["GIT_TAG_NAME=gitTagName()"]) {
          echo env.GIT_TAG_NAME
       }
    }
}


