pipeline {
    agent any
    tools{
        maven 'LOCAL MAVEN3'
    }
    stages{
        stage('build'){
            steps{
                sh 'mvn clean package'
            }
        }
    }

}