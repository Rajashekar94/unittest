

pipeline {
    agent any
    stages {
        stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/Rajashekar94/unittest.git"
            }
        }

        stage ('Artifactory configuration') {
            steps {
                rtServer (
                    id: "artifactory-1",
                    url: "http://localhost:8081/artifactory"
                    
                )

                rtMavenDeployer (
                    id: "test-deploy",
                    serverId: "artifactory-1",
                    releaseRepo: "libs-release-local",
                    snapshotRepo: "libs-snapshot-local"
                )

                rtMavenResolver (
                    id: "test-resolver",
                    serverId: "artifactory-1",
                    releaseRepo: "libs-release",
                    snapshotRepo: "libs-snapshot"
                )
            }
        }

        stage ('Exec Maven') {
            steps {
                rtMavenRun (
                    tool: MAVEN_TOOL, // Tool name from Jenkins configuration
                    pom: 'pom.xml',
                    goals: 'clean install',
                    deployerId: "test-deploy",
                    resolverId: "test-resolver"
                )
            }
        }

        stage ('Publish build info') {
            steps {
                rtPublishBuildInfo (
                    serverId: "artifactory-1"
                )
            }
        }
    }
}

