node {
  try {
    stage('checkout') {
      checkout scm
    }
    stage('build') {
      step ("build") {
        /* execute commands in the scripts directory */
        sh cmake ..
        sh make -j8
      }
    }
    stage('compile') {
      echo "cmake build complete!"
    }
  } finally {
    stage('cleanup') {
      echo "doing some cleanup..."
    }
  }
}
