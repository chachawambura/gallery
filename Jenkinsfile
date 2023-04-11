pipeline {
    agent any 
    tools {
        nodejs 'NodeJS19'
    }
    stages {
        stage('Clone Repository'){
            steps[
                git 'https://github.com/chachawambura/gallery'
            ]
        }
        stage ('Install Dependencies'){
            steps {
                sh 'npm install'
            }
        }
        

    }
}