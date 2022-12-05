pipeline {
  agent any
    stages {
        stage("create lambda zip based on tag") {
          steps {
            script {
              CH_S= sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
            }
            echo "${CH_S}"
            
               script {
                   BIR_SIZE = sh(returnStdout: true, script: "git rev-parse --abbrev-ref HEAD `git rev-list --branches --max-count=1` ")
               }
               echo "${BIR_SIZE}"
              script {
                 GIR_SIZE = sh(returnStdout: true, script: "git branch --show-current")
                sh '''
                    git branch --show-current
                '''
              } 
              echo "${GIR_SIZE}"
               script {
                     DIR_SIZE = sh(returnStdout: true, script: "git describe --tags `git rev-list --tags --max-count=1` ")
                }
                echo "${DIR_SIZE}"
            script {
              HIR_SIZE = sh(returnStdout: true, script: "git symbolic-ref HEAD")
            }
            echo "${HIR_SIZE}"
                
            }
            }
            }
}
