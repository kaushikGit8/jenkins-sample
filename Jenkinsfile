node {
 sh 'echo HelloWorld'

 stage('Checkout') {
        // Checkout files.
        checkout([
            $class: 'GitSCM',
            branches: [[name: 'master']],
            doGenerateSubmoduleConfigurations: false,
            extensions: [], submoduleCfg: [],
            userRemoteConfigs: [[
                name: 'github',
                url: 'https://github.com/kaushikGit8/jenkins-sample.git'
            ]]
        ])
    }

    stage('Build') {
     // Build
    sh 'xcodebuild -scheme "JenkinsSample" -configuration "Debug" build -destination "platform=iOS Simulator,name=iPhone 7,OS=10.1"'
   }

   stage('Test') {
   // Test
   sh 'xcodebuild -scheme "JenkinsSample" -configuration "Debug" test -destination "platform=iOS Simulator,name=iPhone 7,OS=10.1"'
   }

   stage ('Notify') {
       // Notify completion
   sh 'echo Notify if needed completed'
   }
}
