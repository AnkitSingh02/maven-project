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
