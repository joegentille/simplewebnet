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
                sh 'dotnet publish --no-restore --configuration Release --output .\\publish'
            }
        }
//bin\Release\net6.0\publish\
        // stage('Example') {
        //     steps {
        //         script {
        //             def output = sh(returnStdout: true, script: 'pwd')
        //             echo "Output: ${output}"
        //         }
        //     }
        // }
    }
    post {
        success {
            echo 'Build, test, and publish successful!'
        }
    }
}