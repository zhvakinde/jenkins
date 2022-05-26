node {
  //  git url: 'https://github.com/jenkinsci/git-tag-message-plugin'
    TAG_NAME = gitTagName()
  sh (script: "touch ${TAG_NAME}")
 
}

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

