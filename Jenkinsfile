pipeline {
    agent {
        label 'naveen-2'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
      string(name: 'appVersion',defaultValue: '1.0.0', description: 'Application Version?')
    }
    stages {
        stage('Print the version'){
            steps{
                script{
                    echo "application version: $params.appVersion"
                }
            }
        }
    }
    post { 
        always { 
            echo 'Doing Cleanup........!'
            deleteDir()
        }
        success { 
            echo 'Pipeline is success........!'
        }
        failure { 
            echo 'Pipeline is failed..........!'
        }
    }
}