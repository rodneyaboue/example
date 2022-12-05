
pipeline{
  agent any
  stages{
    stage('build'){
      steps
      {
        echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
        powershell "xmake -y"
        // echo  "auteur : ${env.CHANGE_AUTHOR} ${env.CHANGE_AUTHOR_EMAIL} ${env.CHANGE_AUTHOR_DISPLAY_NAME}"
      }
    }
    stage('run'){
      steps
      {
        powershell "git log -1 --pretty=format:'%h - %an, %ar : %s'"
        powershell "xmake run"
      }
    }
    stage('message'){
      steps
      {

        // echo "GIT_AUTHOR_NAME: ${env.GIT_AUTHOR_NAME}"
        // echo "GIT_COMMITTER_EMAIL: ${env.GIT_COMMITTER_EMAIL}"
      }
    }
  }
}
