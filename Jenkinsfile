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
}
