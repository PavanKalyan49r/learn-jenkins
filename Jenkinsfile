pipeline {
    agent {
        node{
            label 'agent-1'
        }
    }

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
}