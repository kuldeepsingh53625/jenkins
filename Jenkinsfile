pipeline {
    agent any
    environment{
        name='kuldeepSingh'
    }
    parameters{
        string(name:'Person',defaultValue: 'Kuldeep', description: 'Who are you')
        booleanParam(name:'isMale',defaultValue: 'TRUE', description: '')
        choice(name:'City',choices: ['jaipur','Mumbai','Pune'], description: '')


    }

    stages {
        stage('Run a command') {
            steps {
                sh '''
                date
                ls
                pwd
                '''
            }
        }
        stage('Deploy On Test') {
            steps {
                echo 'Hello Test'
            }
        }
        
        stage('Deploy on Prod') {
            steps {
                echo 'Hello Prod'
            }
        }
        stage('Environment Variable') {
            steps {
                sh 'echo ${name}'
            }
        }
        stage('input YES or NO') {
            input {
                message "Should we Continue ?"
                ok "Yes you should"
            }
            steps {
                echo "Hello, ${Person}, nice to meet you."
            }
        }
        stage('Parameter') {
            steps {
                sh '''
                echo ${Person}
                echo ${City}
                '''
            }
        }
      
    }
    post{
        always{
            echo 'post will always be executed'
        }
        failure{
            echo 'Failure'
        }
        success{
            echo 'Success'
        }
    }
}
