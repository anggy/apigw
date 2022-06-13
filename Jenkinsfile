pipeline {
    agent any
    stages {
        stage('Continuos Deployment') {
            steps {
                echo 'Starting Continuos Deployment..'   
				sh('ssh -tt wmadmin@10.68.128.3 /opt/softwareag/common/AssetBuildEnvironment/bin/build.sh -Dbuild.output.dir=/opt/image/assets/  -Dapigateway.repo.createFromLocalRepo=true -Dapigateway.repo.localRepo.path=/opt/image/localvcs/ -Dapigateway.is.url=http://35.219.114.242:5555 -Dapigateway.is.username=Administrator -Dapigateway.is.password=biofarma123')
				echo 'CD Started.'   				
            }
        }
        stage('Build Asset Environment') {
            steps {
                echo 'Starting Build Asset Environment..'
				sh('ssh -tt wmadmin@10.68.128.3 /opt/softwareag/common/AssetBuildEnvironment/bin/build.sh -Dbuild.output.dir=/opt/image/assets/ -Dapigateway.is.url=http://35.219.114.242:5555 -Dapigateway.is.username=Administrator -Dapigateway.is.password=biofarma123 -Dapigateway.assets.file=https://raw.githubusercontent.com/anggy/apigw/main/artifacts/asset.json')
				echo 'ABE Completed.'
            }
        }
        stage('Starting Deployer') {
            steps {
                echo 'Starting Deployer....' 
				
				echo 'Deployer Completed'   
            }
        }
        stage('Installing to Staging') {
            steps {
                echo 'Starting Install to Staging....'
				sh ('ssh -tt wmadmin@10.68.128.3 /opt/softwareag/IntegrationServer/instances/default/packages/WmDeployer/bin/Deployer.sh --deploy -dc myDeployment -project deploy-staging -host 35.219.114.242 -port 5555 -user Administrator -pwd biofarma123')
				echo 'Staging OK.'
            }
        }
        stage('Installing to Production') {
            steps {
                echo 'Starting Install to Production....'    
				
				echo 'Production OK.' 
            }
        }
        stage('Deployment Completed !') {
            steps {
                echo 'Continuos Deployment Completed !....'  
					
				echo 'Continuos Deployment Completed !' 
            }
        }
    }
}