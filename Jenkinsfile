pipeline{
    agent any
    environment {
        PATH="$PATH:/opt/apache-maven-3.9.9/bin"
    }
    stages{
        stage('GetCode'){
            steps{
                git branch: 'main', url: 'https://github.com/chandrakatore2004/JAVA-MAVEN-WEB-APP.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('SonarQube Analysis'){
        steps{
        withSonarQubeEnv('sonarqube-25'){
                    sh "mvn sonar:sonar"
         }
        }
        }
        
        
    }
    


    
}