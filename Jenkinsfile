pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh '/opt/softwareag/common/AssetBuildEnvironment/bin/build.sh'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'    
            }
        }
    }
}