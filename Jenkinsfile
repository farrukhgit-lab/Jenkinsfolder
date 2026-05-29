pipeline {
    agent any
    environment {
        name= 'Farrukh'
    }
    parameters {
        string(name: 'person', defaultValue: 'Soha Farrukh', description: "Who are you")
        booleanParam(name: 'ismale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Lahore','Karachi','Peshawar'], description: "")
    }
    stages {
        stage('Run a Command') {
            steps {
                sh '''
                ls
                date
                pwd
                cal 2026
                '''
            }
        }
        stage('Environment Variables') {
            environment {
            uname= 'uFarrukh'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${uname}"'
                
            }
        }
        stage('Parameters') {
            steps {
                echo 'Deploy on Test'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Contiue') {
            input {
                message "Should we continue"
                ok "Yes We Should"
            }
            steps {
                echo 'Deploy on Producation'
            }
        }
        stage('Deploy on Producation') {
            steps {
                echo 'Deploy on Producation'
            }
        }
    }
    post{
        always { 
            echo 'I will always say Hello again!'
        }
        success {
            echo 'Success'
        }
        failure {
            echo 'failure'
        }
    }
}
