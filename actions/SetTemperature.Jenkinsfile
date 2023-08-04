def host_remote = [:]
def temp = 25

properties([
    parameters([
        string(
            defaultValue: '', 
            name: 'host_name', 
            trim: true
        ),
        string(
            defaultValue: 'sv10g', 
            name: 'host_user', 
            trim: true
        ),
        string(
            defaultValue: '25', 
            name: 'temperature', 
            trim: true
        )
    ])
])

node('master'){
    stage("Validation inputs"){
        if(params.host_name == ''){
            currentBuild.result = 'FAILURE'
            error('host_name not set')
        }
        
        if(params.temperature == "" || (params.temperature ==~ /[0-9]+/) == false){
            currentBuild.result = 'FAILURE'
            error('temperature should digit')
        }
    }
}

node(params.host_name){
    stage("Set temperature"){
        sh "python3 ~/system_validation/svt/svtcore/instruments/intec/set_temp.py "+ params.temperature
    }     
}

