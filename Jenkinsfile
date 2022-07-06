pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
                           sh '''
				#!bin/bash
				pip install jupyter_client
				pip install nbconvert
				pip install numpy
				pip install matplotlib
				pip install sklearn
				python3 -m pip install ipykernel
				python3 -m ipykernel install --user
				echo 'Building...'
				jupyter-nbconvert --execute --to=html Jupyter1.ipynb
			      '''
                        }
		}
		stage('Test'){
			steps{
				echo 'Testing..'
			}
		}
	}
}
