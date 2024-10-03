pipeline{
    agent {label 'sonarq'}
    stages{
       /*stage('Git Checkout Stage'){
            steps{
                git branch: 'main', url: 'https://github.com/pratikn05/Sonar-Qube-war-example.git'
            }
         }*/       
       stage('Build Stage'){
            steps{
                sh 'mvn clean install'
            }
         }
       stage('SonarQube Analysis Stage') {
            steps{
                withSonarQubeEnv('sonar-ex') { 
                    sh "mvn clean verify sonar:sonar -Dsonar.projectKey=sonar-ex"
                }
            }
        }
    }
}
