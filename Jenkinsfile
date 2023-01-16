pipeline{
   agent {label 'slave1'}
   stages{
      statge(checkout){
	     steps{
		    
		 
		 }
	  
	  }
	  stage(image build){
	     steps{
		     
			 sh ' docker build -t newimage:1.2.3 . '
		     sh ' docker tag newimage:1.2.3 kirankumartubakad/k8s:newimage '
		 }
	  
	  }
      stage(login to hub){
	     steps{
		   
		   withCredentials([usernamePassword(credentialsId: 'dockerhub-kiran', passwordVariable: 'hub_user_passwd', usernameVariable: 'hub_user')])
		   sh 'docker login -u $hub_user -p $hub_user_passwd'
		 
		 }
	  }   
    stage(push image to hub){
	     steps{
		   
		   sh ' docker push kirankumartubakad/k8s:newimage '
		  
		 }
	  
	  }
   }
}
