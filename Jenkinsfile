pipline
{
	agent any 
	 stages {
	  stage('Pull') {
	    steps{
	     script{
	       checkout([$class: 'GitSCM' , branches: [[name: '*/master']],
	         userRemoteConfigs: [[ 
	           credentialsId: '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',
	           url: 'https://github.com/syrine-bh/CD-project.git']]])
	           }
	           }
	           }
	           }
	           }
