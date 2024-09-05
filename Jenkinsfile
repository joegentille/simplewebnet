pipeline {
    
    agent {
       label "jenkinsagent1"
    }

    stages {
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout'){
            steps {
                checkout scm
                sh 'ls -lah'
                sh 'pwd'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet restore'
                sh 'dotnet build --configuration Release'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test --configuration Release'
            }
        }

        stage('Publish') {
            steps {
                sh 'dotnet publish --configuration Release --output artifacts'
            }
        }

        // stage('Example') {
        //     steps {
        //         script {
        //             def output = sh(returnStdout: true, script: 'pwd')
        //             echo "Output: ${output}"
        //         }
        //     }
        // }
    }
}