pipeline {
    agent {
        node{
            label 'agent-1'
        }
    }
    environment{
        GREETING = 'HELLO JENKINS'
    }
    options{
        timeout(time:1, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
// build
    stages {
        stage('BUILD') {
            steps {
                echo 'BUILDING..'
            }
        }
        stage('TEST') {
            steps {
                echo 'TESTING..'
            }
        }
        stage('DEPLOY') {
            steps {
                sh """ 
                   echo "here i wrote shell script"
                   echo "$GREETING"
                """
            }
        }
    }
    //post build
    post {
        always{
            echo 'i will always say hello again'
        }
        failure{
            echo 'this runs when pipeline is failed, used generally to send some alrets'
        }
        success{
            echo 'i will say hello when pipeline is success'
        }
    }
}