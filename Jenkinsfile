pipeline {
    agent {
        node{
            label 'agent-1'
        }
    }
// build
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('hi') {
            steps {
                echo 'Hi'
            }
        }
        stage('gm') {
            steps {
                echo 'gm '
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