pipeline {
agent any
    
    stages{
    
stage('Imran') {
    // some block
    steps{
        script {
            
        echo 'hello world'
        sh 'chmod 777 ./changelog.sh'
        sh './changelog.sh master development'
        env.WORKSPACE = pwd()

        def version = readFile 'CHANGELOG.md'
        sh 'ls'
        //echo "${version}"
        
        sh 'git tag -a "${BUILD_NUMBER}" -m imran'

 sshagent(['adminjenkinsgithub']) {
                sh 'git push --tags'
        }        
 
      
 
        
        sh 'git cat-file -p ${BUILD_NUMBER}'
        
        
        cleanWs()
    }
    
    }
}
    
}
}

