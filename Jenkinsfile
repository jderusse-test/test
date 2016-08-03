node {

	step([$class: 'GitHubCommitStatusSetter',
      contextSource: [$class: 'ManuallyEnteredCommitContextSource',
                      context: 'Test Context'],
      statusResultSource: [$class: 'ConditionalStatusResultSource',
                           results: [[$class: 'AnyBuildResult',
                                      message: 'test message',
                                      state: 'SUCCESS']]]])

}

