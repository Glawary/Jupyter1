pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
                           sh '''
				#!bin/bash
				echo 'Building...'
				jupyter-nbconvert --to=html Jupyter1.ipynb
			      '''
                        }
		}
		stage('Test'){
			steps{
				echo 'Testing..'
			}
		}
}
                post {
        always {
              
               archiveArtifacts artifacts: '/var/lib/jenkins/workspace/Job3', followSymlinks: false
     
               }
   }

     
}
