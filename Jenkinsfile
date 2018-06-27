pipeline{
    agent any
      environment {
     scannerHome = tool 'Sonar-scanner'
   }
    tools{
        maven 'maven_354'
    }
    stages{
        stage('checkout'){
            steps{
                git 'https://github.com/jglick/simple-maven-project-with-tests'
            }    
        }
        stage('build'){
            steps{
                sh 'mvn install'
            }    
        }
        stage('Sonar'){
            steps{
            withSonarQubeEnv('Sonar') {
                sh '${scannerHome}/bin/sonar-scanner -Dsonar.java.binaries=target/* -Dsonar.projectKey=xlaguarda -Dsonar.sources=.' 
            
        }
    }
}
}
}
