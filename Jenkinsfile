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

        stage('deploy to Prod'){
            steps{
                timeout(time:5,unit:'DAYS'){
                    input message:'是否部署单生产环境中?'
                }
                build job:'deploy-to-prod'
            }
            post{
                success{
                    echo '代码成功部署到生成环境中！！！！！'
                }

                failure{
                    echo '部署失败'
                }
            }
        }
    }
}
