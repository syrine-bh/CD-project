pipline
{
	agent any 
	 stages {
	  stage('Pull') {
	    steps{
	     script{
	       checkout([$class: 'GitSCM' , branches: [[name: '*/master']],
	         userRemoteConfigs: [[ 
	           url: 'https://github.com/syrine-bh/CD-project.git']]])
	           }
	           }
	           }
	           }
	           }
