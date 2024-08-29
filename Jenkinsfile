pipeline {
    agent any

    stages {
        stage('Development') {
            steps {
                script {
                    def repoDir = 'newrepo'
                    if (fileExists(repoDir)) {
                        bat "cd ${repoDir} && git pull"
                    } else {
                        bat "git clone https://github.com/parulpatle/newrepo.git"
                    }
                }
            }
        }

        stage('QA'){
            steps{
                bat '''cd newrepo
                echo >newfile.txt
                echo this is new file>>newfile.txt
                git add .
                git config --global user.email "parulpatle9702@gmail.com"
                git config --global user.name "parulpatle"
                git commit -m "push from Jenkins"
                git push https://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@github.com/parulpatle/newrepo.git'''
            }
        }
        
    }
}
