pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh('ssh wmadmin@10.68.128.3 /opt/softwareag/common/AssetBuildEnvironment/bin/build.sh -Dbuild.output.dir=/opt/image/assets/ -Dapigateway.is.url=https://35.219.114.242:5543 -Dapigateway.is.username=Administrator -Dapigateway.is.password=biofarma123 -Dapigateway.assets.file=/opt/image/assets/artifacts/asset.json')
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