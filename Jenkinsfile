
pipeline {
      agent{
	      label{
		        label'built-in'
				customWorkspace'/mnt/assignmet5/22Q2'
		  } 
	  }
	  stages{
	  
	    /*stage('stage1-22Q2'){
			     steps {
				       sh "docker stop 22Q2-httpd"
				       sh "docker rm 22Q2-httpd"
					   sh "docker rmi httpd"
				       sh "docker volume rm vol-22Q2"
				   }
			   } */
	  
	          stage('docker-volume-22Q2'){
		           steps {
				        sh "docker volume create vol-22Q2"
					    sh "cd /mnt/assignmet5/22Q2 && cp index.html /var/lib/docker/volumes/vol-22Q2/_data"
							
				        }
		    }
			stage('docker-stage-22Q2'){
			      steps{
				        
						sh "docker run --name 22Q2-httpd -itdp 90:80 -v vol-22Q2:/usr/local/apache2/htdocs httpd"
						sh "chmod -R 777 /var/lib/docker/volumes/vol-22Q2/_data/index.html"
                       						
						
				  }
			}
	  }
	  
}

