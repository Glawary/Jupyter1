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
                              ~/.local/bin/kaggle kernels pull glawary/titanic-solution -m
                              ~/.local/bin/kaggle kernels push
                              cd "${WORKSPACE}"
	                      git config --global user.name "Putselovsky Eugene"
                              git config --global user.email "E9315717@yandex.ru"
                              git add .
                              git commit -m "New files"
                              git push origin HEAD:61dd1b9
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
            
}

