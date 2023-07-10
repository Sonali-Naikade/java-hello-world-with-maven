pipeline{
    agent any

    tools {
         maven 'Maven'
         jdk 'java'
    }

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '15823fb2-bc1b-4752-86a1-50e91b015a36', url: 'https://github.com/Sonali-Naikade/java-hello-world-with-maven.git']]])
            }
        }
        stage('build'){
            steps{
               echo "Packaging Aplication..."
               bat 'mvn package'
            }
        }
    }
    post {
        always{
            archiveArtifacts artifacts: '*.*', fingerprint: true
        }
    }
        
}
