pipeline{
      agent{
            label 'slave-label'
      }
            stages{
                  stage(checkout){
                        steps{
                            checkout scm
                              }
                        }
               stage(build){
                     steps{
                       sh 'JAVA_HOME=/home/grras/slavedir/jdk-11.0.24 /home/grras/slavedir/apache-maven-3.9.8/bin/mvn install'
                        }
                       }
                  stage(Deployment){
                        steps{
                              sh 'cp target/Project-3.war /home/grras/slavedir/apache-tomcat-9.0.93/webapps'
                        }
                  }
    }
}

