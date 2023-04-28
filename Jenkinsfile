pipeline {
    agent any
    stages {
        stage('One') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Two') {
            steps{
               input('Do you want to proceed?')
          }
       
        }  
        stage('Three') {
            when {
                not {
                    branch "master"
                }
            }    
            steps {
                echo "Hello"
                }
            } 
        stage('four') {
            parallel {
                stage('Unit Test') {
                    steps {
                        echo "Running the unit test"
                    }
                    stage("Integration Test') {
                          agent {
                              docker {
                                  reuseNode false
                                  image 'ubuntu'
                              }
                          }
                          steps{
                              echo "Running integration test"
                          }
                          }
                          }
    }
}
