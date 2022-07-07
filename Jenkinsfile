pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
                           pwd
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
              
               archiveArtifacts artifacts: 'Jupyter1.html', followSymlinks: false
     
               }
   }

     
}
