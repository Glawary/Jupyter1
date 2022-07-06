pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
				echo 'Building...'
				echo 'jupyter-nbconvert --execute --to=html Jupyter1.ipynb" > run.sh
                                chmod +x run.sh
				./run.sh
			}
		}
		stage('Test'){
			steps{
				echo 'Testing..'
			}
		}
	}
}
