pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image 'openjdk:11'
                    image 'maven' 
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                       sh '''
                            echo "PATH = ${PATH}"
                            echo "M2_HOME = ${M2_HOME}"
                            echo 'Done'
                        ''' 
                        }
                    }
                }
            }
        }
    }
