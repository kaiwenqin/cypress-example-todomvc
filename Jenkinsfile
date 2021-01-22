pipeline {
    agent any
    tools { nodejs "node" }
    options {
        ansiColor('xterm')
        skipDefaultCheckout(true)
    }
    stages {
        stage("Git checkout"){
            git credentialsId: '9b7a89f0-81c8-4b31-a026-9a3a8b962dd3', url: 'https://github.com/kaiwenqin/cypress-example-todomvc.git'
        }  
        stage("Fetch Cypress"){
            steps {
                sh 'CYPRESS_INSTALL_BINARY=/Users/kaiwenqin/Downloads/cypress.zip npm install cypress'
            }
        }
        // stage("Build") {
        //     steps {
        //         sh 'npm install'
        //     }
        // }

        stage("Test") {
            steps {
                sh 'npm run test'
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
