pipeline {
    agent { label 'agent-test' }
    stages {
        stage('Build') {
         when {
                expression { env.Name == 'DS_project_2' }
             }
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh ''' java --version
                python --version'''
            }
        }
        stage('Approval') {
            steps {
                script {
                    // This will show a pop-up in Jenkins asking for approval
                    input message: "Please approve deployment?", ok: "Approve"
                }
            }
        }
        stage('Deploy') {
            steps {
                print ("Deploy")
            }
        }

        stage('Cleanup') {
            steps {
                print("WorkSpace cleanup")
            }
        }
    }
}