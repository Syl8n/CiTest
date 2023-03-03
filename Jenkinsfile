pipeline{
    agent any

    tools{
        maven "Maven"
        jdk "JDK17"
    }

    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/Syl8n/CiTest.git'
            }
        }
        stage('Maven Build'){
            steps{
                sh "mvn -Dmaven.test.failure.ignore=true clean compile"
            }
            post {
                success {
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}