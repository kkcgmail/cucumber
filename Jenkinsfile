pipeline{

    // only run on master for now
	agent {
		label 'master'
	}
    
   

    stages {

        stage ('Compile Stage') {

            steps {

               
                    sh 'mvn clean install'

               

            }
        }
    stage ('Test Stage') {

            steps {

               
                    sh 'mvn test'

              

            }
        }


        stage ('Cucumber Reports') {

            steps {
                cucumber buildStatus: "UNSTABLE",
                    fileIncludePattern: "**/cucumber.json",
                    jsonReportDirectory: 'target'

            }

        }

    }

}
