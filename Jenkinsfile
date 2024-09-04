pipeline {
    
    agent {
       label "jenkinsagent1"
    }

    stages {
        stage('Checkout'){
            steps {
                checkout scm
                sh 'ls -lah'
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