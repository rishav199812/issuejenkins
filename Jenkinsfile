pipeline {
  agent any
    stages {
        stage("create lambda zip based on tag") {
            steps {
               script {
                   BIR_SIZE = sh(returnStdout: true, script: "git rev-parse --abbrev-ref HEAD")
               }
              echo "${BIR_SIZE}"
               script {
                     DIR_SIZE = sh(returnStdout: true, script: "git describe --tags `git rev-list --tags --max-count=1` ")
                }
                echo "${DIR_SIZE}"
                
            }
            }
            }
}
