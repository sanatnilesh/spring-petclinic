pipeline {
    agent any

    stages {
        stage('Checkout'){
             steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/sanatnilesh/spring-petclinic'
             }
        }
        stage('Build') {
            steps{
                sh './mvnw clean package'
            }

            post {
                always {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
