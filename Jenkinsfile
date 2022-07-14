pipeline {
	agent any
        environment {
           export KAGGLE_USERNAME=glawary
           export KAGGLE_KEY=a22b67aa142e4274d1374d2382700567
        }
	stages {
		stage('Build'){
			steps{
                           sh '''
				#!bin/bash
				echo 'Building...'
                                pwd
                                pip3 install -r requirements.txt
                                pip install kaggle       
			      '''
            
                            sh '''
                              #!bin/bash
                              kaggle kernels pull glawary/titanic-solution -m
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
