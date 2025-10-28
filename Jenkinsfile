pipeline{
    tools{
       
        maven 'mymaven'
    }
	agent any
      stages{
           stage('Checkout the code'){
			   steps{
				   echo 'cloning the repo'
				   git 'https://github.com/Manjunath-Kapanaiah/SONAL-REPO.git'
              }
          }
          stage('Compile'){
			  steps{
				  echo 'complie the code again..'
                  sh 'mvn compile'
			  }
		  }
		  stage('CodeReview'){
			  steps{
				  echo 'codeReview'
                  sh 'mvn pmd:pmd'
              }
          }
		  stage('UnitTest'){
			  steps{
				  sh 'mvn test'
			  }
		  }
		  stage('Package'){
			  steps{
				  sh 'mvn package'
			  }
		  }
	  }
}
