pipeline{
    agent any
    environment{
        staging_server='172.174.44.94'
    }

    stages{
        stage{'deploy to remote}{
            steps{
                sh 'scp ${WORKSPACE}/* root@${staging_server}:/var/www/html/'
            }
        }
    }
}