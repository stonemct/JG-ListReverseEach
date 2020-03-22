#!`which env` groovy

node() {

    List LL = ['s1', 's2', 's3']

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
