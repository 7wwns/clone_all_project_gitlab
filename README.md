# clone_all_project_gitlab


script for repo in $(curl -s --header "PRIVATE-TOKEN: PRIVATE_TOKEN_GITLAB" https://<host>/api/v4/groups/<group-id> | jq ".projects[].http_url_to_repo" | tr -d '"'); do git clone $repo; done;



PRIVATE_TOKEN_GITLAB got from edit profile => accesstoken => checked minimum scope is read_api => create token

host = host git
group-id= group of repository
