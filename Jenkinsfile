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
     // Build and Test
    sh 'xcodebuild -scheme "TimeTable" -configuration "Debug" build test -destination "platform=iOS Simulator,name=iPhone 6,OS=10.1"'
   }

   stage ('Notify') {
       // Notify completion
   sh 'echo Notify if needed completed'
   }
}
