node {
  try {
    stage('checkout') {
      checkout scm
    }
    stage('build') {
      sh cd build
      sh cmake ..
      sh make -j8
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