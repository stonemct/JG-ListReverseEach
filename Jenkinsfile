#!`which env` groovy

List LL = []

properties([
    parameters([
        [$class: 'CascadeChoiceParameter',
         choiceType: 'PT_CHECKBOX',
         description: 'Select Environment',
         filterLength: 1,
         filterable: false,
         name: 'Environment',
         script: [
             $class: 'GroovyScript',
             script: [
                 classpath: [],
//                 sandbox: false,
                 sandbox: true,
                 script:
                     'return[\'Development\',\'QA\',\'Staging\',\'Production\']'
             ]
         ]
        ]
    ])
])


node() {

    if ( env.Environment.isEmpty() ) {
        echo "Environment not specified."
        autoCancelled = true
//        error('Aborting the build.')
        LL = [ 's1', 's2', 's3' ]
    }
    else {
        echo "Environment total: ${env.Environment}"
        String[] Env_Array = "${params.Environment}".split(',');
        for (x in Env_Array) {
            echo "ENV: ${x}"
        }
        LL = params.Environment.split(',')
    }
    println 'LL: ' + LL

    LL.each { loopoflist(it) }

    LL.reverseEach { loopoflist(it) }

}

def loopoflist(def ITT) {
    """
This function needs for reuse print and stage phase
input: name of stage
output: none
"""
    println ITT
    stage(ITT)
        {
            println ITT
        }
}
