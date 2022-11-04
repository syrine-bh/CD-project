pipeline
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
	 stage('build') {
	    steps{
	     script{
	     
	     	  sh "npm install -g @angular-devkit/build-angular",
	          sh "sudo ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
	           }
	           }
	           }
	           }
	           }
