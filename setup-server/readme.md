

# Lien important 
https://clear.ml/docs/latest/docs/deploying_clearml/clearml_server_linux_mac
https://github.com/clearml/clearml-server/issues/280


# Tuto : 
Dans un DND ça passe par mais en SSH ça peut se faire : 

tutoriel à faire : 

remplacer FOLDER_DIR par le bon folder ( il peut ne pas être /opt/clearml pour éviter les sudo )


curl https://raw.githubusercontent.com/clearml/clearml-server/master/docker/docker-compose.yml -o FOLDER_DIR/docker-compose.yml


export CLEARML_AGENT_ACCESS_KEY=generate_access_key_here
export CLEARML_AGENT_SECRET_KEY=generate_secret_key_here
export CLEARML_HOST_IP=HOST_IP
export CLEARML_AGENT_GIT_USER=git_username_here
export CLEARML_AGENT_GIT_PASS=git_password_here


sudo chown -R 1000:1000 /mnt/bdisk/bournez/clearml-server/clearml
( pour faire cette étape, on peut faire du privileged de docker :)) 

sudo chown -R 1000:1000 /mnt/bdisk/bournez/clearml-server/clearml
<!-- docker run --rm -v /mnt/bdisk/bournez/clearml-server/clearml:/data alpine chown -R 1000:0 /data -->
run in case this one :
<!-- docker exec -it clearml-elastic sh -c "id" -->

docker compose -fFOLDER_DIR/docker-compose.yml down
docker compose -f FOLDER_DIR/docker-compose.yml up -d

docker compose -f FOLDER_DIR/docker-compose.yml logs 


Remplacer dans le docker-compose le path FOLDERCLEARML/ par FOLDER_DIR :) 

# Si ça marche pas
checker 


docker exec -it clearml-elastic sh -c "id"


ls -ld FOLDER_DIR/


( voir ça https://github.com/clearml/clearml-server/issues/280
) 
# Si ça marche
checker ça http://localhost:8080/settings/workspace-configuration
