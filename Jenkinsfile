properties([
    buildDiscarder(logRotator(numToKeepStr: '5')),
    pipelineTriggers([
        pollSCM('H/5 * * * *'),
        cron('@midnight')
    ]),
    parameters([
        string(defaultValue: 'Jenkins Techlab', description: 'Who to greet?', name: 'Greetings_to'),
        choice(choices: ['a','b','c','d'].join("\n"), description: 'Do the choice', name: 'auswahl')
    ])
])

timestamps() {
    timeout(time: 10, unit: 'MINUTES') {
        node {
            stage('Greeting') {
                echo 'Hello, ' + params.Greetings_to + '!'
            }
        }
    }
}
