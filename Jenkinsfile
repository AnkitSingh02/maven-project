pipeline 
{
    agent any    
    tools
    {
        maven 'System_Maven'
        jdk 'System_MAC_JDK'
    }

     stages{
	stage('Build'){
	   steps{
		sh 'mvn clean package'
		}
	   post {
		success{
			echo 'Now Archiving...'
			archiveArtifacts artifacts: '**/target/*.war'
			}
		  } 
	        }		
	 stage ('Deploy To Staging'){
           steps{
                build job: 'Deploy_To_Staging(Maven_Project)'
                }
            }
	     
	 stage ('Deploy To Production'){
		 steps{
			 timeout(time:5, unit:'DAYS'){
			 	input message: 'APPROVE PRODUCTION DEPLOYMENT ? ' 
			 }
		 build job: 'Deploy_To_Production(Maven_Project)'
		  }
		 
		 post {
		success{
			echo 'Code Deployed to Production'
			}
		failure{
			echo 'Deployment Failed !!!'
			 }
		  } 
	 }
	}
}	
	
/**          
      stages
      {
        stage('Init')
        {
          steps
          {
          echo "Testing..."         
        }     
      }
        stage('Build')
        {
        steps
          {
            echo "Building..."         
          }     
      }
        stage('Deploy')
        {
          steps
          {
            echo "Code Deployed..."         
        }     
      }
   }
}
*/
