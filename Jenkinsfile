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
		stage('install') {
	    	steps{
	     		script{
	     	  		sh "npm install"
	          	}
	        }
	    }
	 	stage('build') {
	    	steps{
	     		script{
<<<<<<< HEAD
	              sh "ansible-playbook ansible/inventory/build.yml  -i /ansible/inventory/host.yml -e 'ansible_become_password=ansible'"
=======
	              sh "ansible-playbook ansible/build.yml  -i /ansible/inventory/host.yml -e 'ansible_become_password=ansible'"
>>>>>>> 6b5df9f59b145a508d7582646e523cb58f927640
	           }
	        }
	    }
	    	stage('docker') {
	    	steps{
	     		script{
	          		sh "ansible-playbook ansible/docker.yml  -i /ansible/inventory/host.yml -e 'ansible_become_password=ansible'"
	           }
	        }
	    }
	}
}
