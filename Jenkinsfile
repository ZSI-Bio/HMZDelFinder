pipeline {
     agent any
    stages {

         stage('Build R package') {
                             steps {
                                 echo 'Building R package....'
                                 sh "cd .. && R CMD build HMZDelFinder/ && curl -v --user ${NEXUS_USER}:${NEXUS_PASS} --upload-file HMZDelFinder_0.0.1.tar.gz http://zsibio.ii.pw.edu.pl:50007/repository/r-zsibio/src/contrib/HMZDelFinder_0.0.1.tar.gz"
                                    }

                  }
            }
         }