pipeline {
    agent any
    tools{
        maven 'LOCAL MAVEN3'
    }
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo '开始存档...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage('deploy to staging'){
            steps{
                build job:'deploy-to-staging'
            }
        }
    }
}
