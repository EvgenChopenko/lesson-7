node {
  stage 'Build image' 
  git 'https://github.com/EvgenChopenko/lesson-7.git' 
  def docker_image = docker.build 'my-image'

  stage 'Test | workdir '
    docker_image.withRun {c ->
    sh 'ls'
    }

  stage 'Push | Apply'
  try {
      timeout(time:10,unit: 'SECONDS'){

    response = input message: 'User input required', ok: 'Deploy!' 
      }
  }
  catch {
      response = 'stop'
  }       
}