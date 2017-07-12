pipeline {
     agent any
    stages {

         stage('Build R package') {
                            when {
                                  branch 'master'
                                 }
                             steps {
                                 echo 'Building R package....'
                                 sh "R CMD build ./ && curl -v --user ${NEXUS_USER}:${NEXUS_PASS} --upload-file HMZDelFinder_0.0.1.tar.gz http://zsibio.ii.pw.edu.pl:50007/repository/r-zsibio/src/contrib/HMZDelFinder_0.0.1.tar.gz"

                                echo "Triggering zsi-bio-docker-image build proceses"
                                build job: 'ZSI-Bio/zsi-bio-docker-image/master', wait: false
                                    }

                  }
            }
         }