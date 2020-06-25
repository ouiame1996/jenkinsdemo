#!/usr/bin/env groovy

pipeline {

	stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
	
    agent {
        docker {
            image 'node:6-alpine'
            args '-u root -p 3000:3000'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
            }
        }
    }
}
