node {
    git url: 'https://github.com/jenkinsci/git-tag-message-plugin'
    env.GIT_TAG_NAME = gitTagName()
    echo env.GIT_TAG_NAME
}

/** @return The tag name, or `null` if the current commit isn't a tag. */
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

