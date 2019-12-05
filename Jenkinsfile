pipeline {
    agent {
     node { 
        label 'node1'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                echo "Middle Stage"
            }
           // post {
             //   always {
                   // junit 'target/surefire-reports/*.xml'
              //  }
         //   }
        }
        stage('Deliver') {
            steps {
				echo "Testing phase"
                 sh 'curl -uadmin:AP5iMVLgKrY4yodTi9MeqgUPJiS -T /home/jenkins/node/workspace/Mule_CICD/target/maven-mule-plugin-1.10-SNAPSHOT.jar "http://mdcassimsait.southindia.cloudapp.azure.com:8081/artifactory/example-repo-local/$BUILD_NUMBER/maven-mule-plugin-1.10-SNAPSHOT.jar"'
		}
        }
    }
}
