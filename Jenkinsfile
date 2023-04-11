pipeline {
    agent any 
    tools {
        nodejs 'NodeJS19'
    }
    stages {
        stage('Clone Repository'){
            steps[
                git 'https://github.com/chachawambura/gallery.git'
            ]
        }
        stage ('Install Dependency'){
            steps {
                sh 'npm install'
            }
        }
           

    }
}