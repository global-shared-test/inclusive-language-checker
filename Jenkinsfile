import com.global.hooks.InclusivityCheck

setup

def inclusiveHook = new InclusivityCheck (
    steps: this,
)

buildGradle([
    aws: [role: "jenkins-devops", account: "873744935058"],
    images: ["inclusive-language-test": "."],
    hooks: [InclusivityCheck],
    gradleImage: "gradle",
    gradleTag: "7.3-jdk17"
])
