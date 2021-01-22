pipeline {
    agent any
    tools { nodejs "node" }
    options {
        ansiColor('xterm')
        skipDefaultCheckout(true)
    }
    stages {
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
