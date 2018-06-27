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
        stage('stage-1'){
            steps{
                sh 'mvn clean package'
            }    
        }
        stage('stage-2'){
            steps{
            archive 'target/surefire-reports/*'
            archive 'target/*.jar'    
            }
        }
    }
}

