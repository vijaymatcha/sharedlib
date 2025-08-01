def notifyBuild(String buildStatus = 'STARTED') {
  // build status of null means successful
  buildStatus =  buildStatus ?: 'SUCCESS'

  // Default values
  def colorName = 'RED'
  def colorCode = '#FF0000'
  def subject = "${buildStatus}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'"
  def summary = "${subject} (${env.BUILD_URL})"

  // Override default values based on build status
  if (buildStatus == 'STARTED') {
    color = 'YELLOW'
    colorCode = 'F5B027'
  } else if (buildStatus == 'SUCCESS') {
    color = 'Fuchsia'
    colorCode = 'FF00FF'
  } else {
    color = 'RED'
    colorCode = '#FF0000'
  }

  // Send notifications
   slackSend (color: colorCode, message: summary) //, channel: '#prod-team')
  //slackSend (color: colorCode, message: summary, channel: '#dev-team')
 
}

