node('master'){
	   
	   stage('Git checkout'){
	                  git 'https://github.com/Gajalakhsmi98/GeneralSpringBootProgExce.git'
	              }


	   stage('Build approval') 
        {
                          input "Build the app?"
        }
	 
	   stage('Build'){
	             sh '/opt/maven/bin/mvn clean install'
	         }
	         	   stage('Deployment approval') 
        {
                          input "Deploy the app?"
        }
	            stage('Deploy'){
             sh '/opt/maven/bin/mvn clean deploy -DaltDeploymentRepository=internal.repo::default::http://admin:admin123@3.18.111.123:8081/nexus/content/repositories/snapshots/'
         }
	
	stage('Running java backend application'){
	sh 'export JENKINS_NODE_COOKIE=dontKillMe ;nohup java -Dspring.profiles.active=uat -jar $WORKSPACE/target/*.jar &'
	}
	stage('Slack it'){
           
                slackSend channel: '#jenkins', 
                          message: 'Parking backend application deployed  completed successfully'
            
        }
	}
