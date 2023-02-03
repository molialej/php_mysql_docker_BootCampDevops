pipeline{
    agent any
    environment{
        staging_server="localhost"
    }

    stages{
        stage('Deploy to Remote'){
            steps{
                sh '''
                    for fileName in `find ${WORKSPACE} -type f -mmin -10 | grep -v ".git" | grep -v "Jenkinsfile"`
                    do
                        echo ${fileName} | sed 's/'"${JOB_NAME}"'/ /' | awk
                        scp -r ${WORKSPACE}/* root@${staging_server}:/var/www/html/
                    done
                '''
            }
        }
    }
}