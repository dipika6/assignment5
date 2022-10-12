pipeline {
      agent{
	      label{
		        label'built-in'
				customWorkspace'/mnt/assignmet5/22Q1'
		  } 
	  }
	  stages{
	  
	    stage('stage1-22Q1'){
			     steps {
				       sh "docker stop 22Q1-httpd"
				       sh "docker rm 22Q1-httpd"
					   sh "docker rmi httpd"
				       sh "docker volume rm vol-22Q1"
				   }
			   } 
	  
	          stage('docker-volume-22Q1'){
		           steps {
				        sh "docker volume create vol-22Q1"
					    sh "cd /mnt/assignmet5/22Q1 && cp index.html /var/lib/docker/volumes/vol-22Q1/_data"
							
				        }
		    }
			stage('docker-stage-22Q1'){
			      steps{
				        
						sh "docker run --name 22Q1-httpd -itdp 80:80 -v vol-22Q1:/usr/local/apache2/htdocs httpd"
						sh "chmod -R 777 /var/lib/docker/volumes/vol-22Q1/_data/index.html"
                       						
						
				  }
			}
	  }
	  
}


