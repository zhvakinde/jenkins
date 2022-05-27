node {
    git branch: 'main', url: 'https://github.com/zhvakinde/jenkins'
    env.GIT_TAG_NAME = gitTagName()
    echo env.GIT_TAG_NAME
}

String gitTagName() {
    commit = getCommit()
    if (commit) {
       return  sh(script: "git describe --tags ${commit}", returnStdout: true)?.trim()
    }
    return null
}
String getCommit() {
    return sh(script: 'git rev-parse HEAD', returnStdout: true)?.trim()
}


