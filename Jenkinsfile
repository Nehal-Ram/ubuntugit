pipeline {
        agent any
                stages {
                        stage('One') {
                                steps {
                                        echo 'Hi,stage one executed'
                             }
                }
                
                stage('Two') {
                        steps {
                                input('Do u want to continue')
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
                
                stage('Four') {
                                 parallel {
                                        stage('Unit Test') {
                                                            Steps {
                                                                  echo "Running unit test"
                                                                  }
                                         }
                                         stage('Integration test') {
                                                               agent {
                                                                      docker {
                                                                              reuseNode false
                                                                              image 'ubuntu'
                                                                      }
                                                                }
                                                                steps {
                                                                      echo 'Running integ test'
                                                                }
                                         }
                               }
}
}
}

                
                
                            
