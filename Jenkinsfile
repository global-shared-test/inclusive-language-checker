import com.global.hooks.InclusivityCheck

setup

def inclusivityHook = new InclusivityCheck(
  steps: this
)

buildGradle([
    aws: [role: "jenkins-devops", account: "873744935058"],
    deopendencyTrack: true,
    wrapper: true,
    nexus: true,
    images: ["inclusive-language": "."],
    registry: "873744935058.dkr.ecr.eu-west-1.amazonaws.com",
    team: "jl",
    hooks: [InclusivityCheck],
    gradleImage: "gradle",
    gradleTag: "7.3-jdk17"
])