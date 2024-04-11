pipeline {
    agent any 
              tools {
            maven 'maven383'
          }

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm: [$class: 'GitSCM', userRemoteConfigs: [[url: 'https://github.com/MezghichGit/jenkins_sonar_ams_data.git']]]
            }
        }

        stage('Sonarqube') {
            steps {
                sh '''
                mvn sonar:sonar \
                -Dsonar.projectKey=ams_data \
                -Dsonar.host.url=http://jenkins.smart-it-partner.com:9010 \
                -Dsonar.login=d434c557f66886c9e952f9c0f511555a1be630d3
                '''
            }
        }
    }
}
