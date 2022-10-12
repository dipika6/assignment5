
pipeline {
      agent{
	      label{
		        label'built-in'
				customWorkspace'/mnt/assignmet5/22Q3'
		  } 
	  }
	  stages{
	  
	    /*stage('stage1-22Q3'){
			     steps {
				       sh "docker stop 22Q3-httpd"
				       sh "docker rm 22Q3-httpd"
					   sh "docker rmi httpd"
				       sh "docker volume rm vol-22Q3"
				   }
			   } */
	  
	          stage('docker-volume-22Q3'){
		           steps {
				        sh "docker volume create vol-22Q3"
					    sh "cd /mnt/assignmet5/22Q3 && cp index.html /var/lib/docker/volumes/vol-22Q3/_data"
							
				        }
		    }
			stage('docker-stage-22Q3'){
			      steps{
				        
						sh "docker run --name 22Q3-httpd -itdp 70:80 -v vol-22Q3:/usr/local/apache2/htdocs httpd"
						sh "chmod -R 777 /var/lib/docker/volumes/vol-22Q3/_data/index.html"
                       						
						
				  }
			}
	  }
	  
}

