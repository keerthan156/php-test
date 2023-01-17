pipeline{
    agent any
    environment{
        staging_server='172.174.44.94'
    }

    stages{
        stage('deploy to remote){
            steps{
                sh '''
                    for fileName in `find ${WORKSPACE} -type f -mmin -10 | egrep -v ".git | Jenkinsfile"`
                    do
                        echo {$fileName} | sed 's/'"${JOB_NAME}"/ /'
                        scp -r ${WORKSPACE}/* root@${staging_server}:/var/www/html/
                    done
                '''
            }
        }
    }
}
