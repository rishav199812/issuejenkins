pipeline {
  agent any
  environment {
        CURRENT_BRANCH_NAME = "${GIT_BRANCH.split('/').size() > 1 ? GIT_BRANCH.split('/')[1..-1].join('/') : GIT_BRANCH}"
    }
    stages {
        stage("create lambda zip based on tag") {
            steps {
               script {
                   BIR_SIZE = sh(returnStdout: true, script: "git rev-parse --abbrev-ref HEAD")
               }
               echo "${BIR_SIZE}"
              script {
                 GIR_SIZE = sh(returnStdout: true, script: "git branch --show-current")
              } 
              echo "${GIR_SIZE}"
               script {
                     DIR_SIZE = sh(returnStdout: true, script: "git describe --tags `git rev-list --tags --max-count=1` ")
                }
                echo "${DIR_SIZE}"
            }
        }
        stage('Set branch name') {
            steps {
                script{
                    currentBuild.displayName = "#"+currentBuild.number+": "+CURRENT_BRANCH_NAME
                }
            }
        }
                
   
            }
}

