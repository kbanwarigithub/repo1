pipeline{
    tools{
        maven 'mymaven'
    }
    agent any
    stages{
        stage('Checkout'){
            steps{
                git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
            }
        }
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
          
        }
        stage('CodeReview'){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage ('UnitTest'){
            steps{
                sh 'mvn test'
            }
        }
        stage('MetricCheck'){
            steps{
                sh 'mvn cobertura:cobertura -Dcobertura.report.format'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
    }
}
