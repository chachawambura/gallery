pipeline {
    agent any 
    tools {
        nodejs 'NodeJS19'
    }
    stages {
        stage('Clone Repository'){
            steps{
                git 'https://github.com/chachawambura/gallery.git'

            }
                
            
        }
        stage ('Install Dependency'){
            steps {
                sh 'npm install'
            }
        }
        stage ('Tests'){
            post {
                failiure{
                    mail bcc: '', body: 'BRO! Your project has failed. Please check the tests. ', cc: '', from: '', replyTo: '', subject: 'Build Failure', to: 'paul.wambura@student.moringaschool.com'
                }
            }
            steps{
                sh 'npm test'   
            }
        }


        
           

    }
}