pipeline {
	agent any
	stages {
		stage('Build'){
			steps{
                           sh '''
				#!bin/bash
				echo 'Building...'
                                pwd
                                pip3 install -r requirements.txt       
			      '''
            
                            sh '''
                              #!bin/bash
                              ~/.local/bin/kaggle competitions list
                              '''
                        }
		}
		stage('Test'){
			steps{
                              sh '''
                                #!bin/bash
				echo 'Testing..'
                              '''
			}
		}
}
                post {
        always {
              
               archiveArtifacts artifacts: 'Jupyter1.html', followSymlinks: false
     
               }
   }

     
}
