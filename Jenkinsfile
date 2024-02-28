pipeline {
    agent 'none'
    triggers { 
        pollSCM ('* * * * *')
    }
    parameters {
        string (name : 'amar_andole', defaultValue : 'input-amar', description : 'this is a string parameter') 
    }

    stages {
        stage ('build') {
            agent {
                label 'slave1'
            }
        steps {
            sh '''
            echo "amar"
            echo $amar_andole
            sleep 10
            '''
        }
        }
        stage ('test') {
            agent {
                label 'slave2'
            }
        steps {
          script {
            echo "${params.amar_andole}"
          }
        }
        }
            }
        }
