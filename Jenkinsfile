pipeline {
    agent any
    tools {
        maven:'m3'
    }
}
        stages{
        stage("Checkout SCM"){
            steps{
                git branch: 'master', url: 'https://github.com/naren1979/spring-prj3.git'
                echo "========executing A========"
            }
     
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "executed successfully"
                }
                failure{
                    echo "========A execution failed========"
                }
                
            }

        stage("Compile"){
            steps{
                sh 'mvn compile'
                echo "========executing A========"
            }
     
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "executed successfully"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }

        stage("Test"){
            steps{
                sh 'mvn test'
                echo "========executing A========"
            }
     
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "executed successfully"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
