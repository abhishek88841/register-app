pipeline {
    agent any
    tools {
        jdk 'java17'
        maven 'Maven3'
    }
  
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'gitid', url: 'https://github.com/abhishek88841/register-app.git'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

       }

       stage("Test Application"){
           steps {
                 sh "mvn test"
           }
       }

       
    }

        
}   

