pipeline {
    agent any
    tools{
        maven 'LOCAL_MAVEN3'
    }
    stages{
        stage('build'){
            steps{
                sh 'mvn clean package'
            }
        }
    }

}