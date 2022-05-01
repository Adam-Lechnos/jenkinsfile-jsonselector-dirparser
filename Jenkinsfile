//code snippet - directory parser for json selector
dir_list_root = sh(label: 'Check create folder directory structure for JSON Selector, script: 'ls -l test | grep '^d' foo/bar', returnStdout: true).trim()'

if ( dir_list_root ) {

  if (json_selector.size() > 0) {

    json_selector.split(",").each { newInput -> 
      file_list += "foo/bar/$aws_region/$role_account_env/$newInput," 
    }

    file_list = file_list.drop(4)
    file_list = file_list.reverse().drop(1).reverse()
    splitter = ","

    echo "--------------------------------------------------------------------------"
    echo "JSON Selector is active for folder $aws_region/$role_account_env/ "
    echo "--------------------------------------------------------------------------"

  } else {

    file_list = sh (label: 'Retrieve file list', script: 'find foo/bar/$aws_region/$role_account_env/ -type f', returnStdout: true).trim()
    splitter = "\n"

    echo "Deploying all JSON files for folder $aws_region/$role_account_env/"

  }


} else {


  if ( json_selector.size() > 0 ) {
  
    json_selector.split(",").each { newInput ->
      file_list += "foo/bar/$newInput,"
    }

    file_list = file_list.drop(4)
    file_list = file_list.reverse().drop(1).reverse()
    splitter = ","

    echo "----------------------------------------------"
    echo "JSON Selector is active for root create folder"
    echo "----------------------------------------------"

  } else {

    file_list = sh (label: 'Retrieve file list', script: 'find foo/bar/ -maxdepth 1 -type f', returnStdout: true).trim()
    splitter = "\n"

    echo "Deploying all JSON files for root create folder"

  }

  
}
