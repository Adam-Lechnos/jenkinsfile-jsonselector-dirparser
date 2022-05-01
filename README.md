# jenkinsfile-jsonselector-dirparser
Counterpart groovy jenkinsfile script for the [json selector](https://github.com/Adam-Lechnos/jenkins-multiselect-repo-data) against structured json git directories

#### Intended Audienace
* Devops

#### Usage
*  Edit the Jenkinsfile snippet and replace `foo/bar` with the persistent directroy structure as determined within the counterpart [json selector](https://github.com/Adam-Lechnos/jenkins-multiselect-repo-data) for the active choice dropdown within Jenkins.
*  Place the script withing a step where by which the selected data within the dropdown should be consumed, usually by the `groovy.json.JsonSlurper()` function.
