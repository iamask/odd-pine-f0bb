#!/usr/bin/env groovy

pipeline {
    agent any
    tools {
        nodejs 'node-8.1.3'
    }
    stages {
        stage('Build') {
            steps {
                sh 'nodejs --version'
                sh 'npx wrangler deploy'
 
            }
        }
        stage('Test') {
            steps {
                sh 'nodejs --version'
                sh 'npx wrangler deploy'
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
