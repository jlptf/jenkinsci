node{
  def appName = 'jenkinsci'
  def tag = "${env.BUILD_NUMBER}"
  def img = "jlptf/${appName}-${env.BRANCH_NAME}"
  def imgWithTag = "${img}:${tag}"

  checkout scm

  try{
    stage '建立映像檔'
    env.currentStage = '建立映像檔'
    sh("docker build -t ${imgWithTag} .")

    stage '執行測試'

    stage '放置映像檔'
    env.currentStage = '放置映像檔'

    stage '部署程式'
    env.currentStage = '部署程式'

    sleep 30

    stage '移除舊映像檔'
    env.currentStage = '移除舊映像檔'
    
  } catch(e){
  }
}