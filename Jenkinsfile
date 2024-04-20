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
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('check params'){
            steps{
                sh """
                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
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