pipeline {
   agent any
   stages{
    stage('Codescsn'){
        steps{
            sh 'trivy fs . -o result.html'
        }
    }
    stage('dockerImageBuild'){
        steps{
            sh 'docker -v'
        }
}
    stage('pushIamge'){
        steps{
            sh 'docker ps'
        }
    }
   } 
}