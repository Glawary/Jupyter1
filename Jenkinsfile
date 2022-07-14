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
                              ~/.local/bin/kaggle competitions download -c titanic
                              ~/.local/bin/kaggle kernels pull glawary/titanic-solution -p /home/eugene/jupyter1/Jupyter1/ -m
                              cd ~/jupyter1/Jupyter1/
                              git add .
                              git commit -m "1"
                              git push origin
                              ~/.local/bin/kaggle kernels push
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
