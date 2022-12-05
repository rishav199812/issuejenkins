pipeline {
  agent any
    stages {
        stage("create lambda zip based on tag") {
          steps {
            script {
            GIT_BRANCH_LOCAL = sh (
        script: "echo $Branch | sed -e 's|origin/||g'",
        returnStdout: true
    ).trim()
            }
    echo "Git branch: ${GIT_BRANCH_LOCAL}"
            //echo GIT_BRANCH %GIT_BRANCH%
            //echo GIT_LOCAL_BRANCH %GIT_LOCAL_BRANCH%
              }
        }
    }
}
