setup

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

buildGradle([
    aws: [role: "jenkins-devops", account: "873744935058"],
    images: ["inclusive-language-test": "."],
    hooks: [InclusivityCheck]
])
