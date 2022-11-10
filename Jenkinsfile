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
	              sh "ansible-playbook Ansible/docker.yml  -i /Ansible/inventory/host.yml -e 'ansible_become_password=ansible'"
	           }
	        }
	    }
	    	stage('docker') {
	    	steps{
	     		script{
	          		sh "ansible-playbook Ansible/docker-registry.yml  -i /Ansible/inventory/host.yml -e 'ansible_become_password=ansible'"
	           }
	        }
	    }
	}
}
