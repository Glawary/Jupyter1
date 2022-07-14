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
                              ~/.local/bin/kaggle competitions download -c Titanic - Machine Learning from Disaster
                              ~/.local/bin/kaggle kernels pull glawary/titanic-solution -m
                              ~/.local/bin/kaggle kernels push
                              '''
                        }
		}
		stage('Test'){
			steps{
                              sh '''
                                #!bin/bash
				echo 'Testing..'
                                jupyter-nbconvert --execute --to=html titanic-solution.ipynb
                              '''
			}
		}
}
                post {
        always {
              
               archiveArtifacts artifacts: 'titanic-solution.html', followSymlinks: false
     
               }
   }

     
}
