node {
        def MVN
        stage("Checkout SCM") {
            git branch: 'main', credentialsId: 'b90cc235-1a2a-4acb-a37b-3cd5cd26bc3e', url: 'git@github.com:aragastmatb/simple_mvn.git'
            MVN = tool 'mvn385'
        }
        stage("Execute Maven") {
            withEnv(["MVN_HOME=$MVN"]){
                if (env.PROD == 'true'){
                    sh "$MVN_HOME/bin/mvn clean package"
                } else {
                    sh "$MVN_HOME/bin/mvn clean compile"
                }                
            }
                
        }
}
