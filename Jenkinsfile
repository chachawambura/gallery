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
                failure{
                    mail bcc: '', body: 'BRO! Your project has failed. Please check the tests. ', cc: '', from: '', replyTo: '', subject: 'Build Failure', to: 'paul.wambura@student.moringaschool.com'
                }
            }
            steps{
                sh 'npm test'   
            }
        }
        stage ('Deploy to Heroku'){
            steps{
                withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS')]) {
                    sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/gallery-ip.git master'
            }
            }
        }
        stage ('Send Message to Slack'){
            steps{
                slackSend channel: '#project-1', message: 'Build No. ${env.BUILD_NUMBER} has been successful  (<|Open>)', teamDomain: 'paulip1', tokenCredentialId: 'slack'
            }
        }


        
           

    }
}