setup

<<<<<<< HEAD
class InclusivityCheck{
    def steps
    Map buildStep

    def postTag(Map data) {
        String ws = data.ws

        steps.node {
            steps.ws(ws) {
                def name = this.buildStep.name
                def cmd = this.buildStep.command

                steps.stage(name) {
                    steps.sh cmd
                    steps.sh "woke"
                }
            }
        }
    }
}

def inclusiveHook = new InclusivityCheck (
    steps: this,
    buildStep: [
        name: "Run Inclusive Language Check, please wait...",
        command: "curl -sSfL https://git.io/getwoke | bash -s -- -b /usr/local/bin"
    ]
)

gradleDocker([
    aws: [role: "jenkins-devops", account: "873744935058"],
    images: ["getwoke/woke:0.19.0": "."],
    registry: "873744935058.dkr.ecr.eu-west-1.amazonaws.com",
    team: "jl",
    hooks: [InclusivityCheck],
=======
buildGradle([
    aws: [role: "jenkins-devops", account: "873744935058"],
    images: ["inclusive-language-test": "."],
>>>>>>> 81ce89e351fbdc08ff69f3cffa1dbb357eaa6b4f
    gradleImage: "gradle",
    gradleTag: "7.3-jdk17"
])
