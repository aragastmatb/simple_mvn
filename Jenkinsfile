node {
        def MVN
        stage("Checkout SCM") {
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
