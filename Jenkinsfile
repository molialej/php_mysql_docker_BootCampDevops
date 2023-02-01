pipeline{
    agent any

    stage{
        stage('Deploy to Remote'){
            steps{
                sh 'scp ${WORKSPACE}/* root@localhost:/var/www.html/'
            }
        }
    }
}