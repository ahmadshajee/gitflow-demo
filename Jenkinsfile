pipeline {
    agent any

    tools {
        gradle 'Gradle_8' // Ensure "Gradle_8" is set up in Jenkins Global Tools
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ahmadshajee/gitflow-demo.git', branch: 'develop'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew clean build'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
            }
        }
    }
}

