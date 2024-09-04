pipeline {
    agent any

    stages {
        stage('Checkout'){
            steps {
                checkout scm
            }
            steps {
                script {
                    def output = sh(returnStdout: true, script: 'pwd')
                    echo "Output: ${output}"
                }
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