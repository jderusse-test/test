node {
    stage "CS"
    setGitHubPullRequestStatus context: 'CS', state: 'PENDING'
    setGitHubPullRequestStatus context: 'Unit testing', state: 'PENDING'
    setGitHubPullRequestStatus context: 'deployment', state: 'PENDING'

    try {
        sh('sleep 5')
        setGitHubPullRequestStatus context: 'CS', state: 'SUCCESS'
    } catch (error) {
        setGitHubPullRequestStatus context: 'CS', state: 'FAILURE'
        setGitHubPullRequestStatus context: 'Unit testing', state: 'ERROR'
        setGitHubPullRequestStatus context: 'deployment', state: 'ERROR'
        throw e
    }

    try {
        sh('sleep 5')
        setGitHubPullRequestStatus context: 'Unit testing', state: 'SUCCESS'
    } catch (error) {
        setGitHubPullRequestStatus context: 'Unit testing', state: 'FAILURE'
        setGitHubPullRequestStatus context: 'deployment', state: 'ERROR'
        throw e
    }

    try {
        sh('sleep 5')
        setGitHubPullRequestStatus context: 'deployment', state: 'SUCCESS'
    } catch (error) {
        setGitHubPullRequestStatus context: 'deployment', state: 'FAILURE'
        throw e
    }
}
