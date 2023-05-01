pipeline {
  agent any
  stages {
    stage('Clone repository') {
      steps {
        git branch: 'master', url: 'https://github.com/brijeshsmita/my-jenkins-jobs-backup-may2023.git'
      }
    }
    stage('Push to GitHub') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'brijeshsmita', usernameVariable: 'GITHUB_USERNAME', passwordVariable: 'GITHUB_PASSWORD')]) {
          bat 'git add .'
          bat 'git commit -m "Pushed to Git"'
         // bat 'git remote rm origin'
         // bat 'git remote add origin https://github.com/brijeshsmita/my-jenkins-jobs-backup-may2023.git'
          bat 'git config --global user.email "brijeshsmita@gmail.com"'
          bat 'git config --global user.name "brijeshsmita"'          
          //sh "git config credential.helper 'store --file ~/.git-credentials'"
          //sh "echo https://$GITHUB_USERNAME:$GITHUB_PASSWORD@github.com >> ~/.git-credentials"
          bat 'git push -u origin master'
          
        }
      }
    }
  }
}
