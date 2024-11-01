# vespa-basic-search
# Steps to run:
- Install Colima and docker(Mac systems)
- Verify of docker memory is atleast 4GB
`docker info | grep "Total Memory"`
- To increase the memory start colima with
`colima start --memory 5`
- Install Vespa
`brew install vespa-cli`
- Set target to local`vespa config set target local`
- Pull the vespa docker image`docker pull vespaengine/vespa`
- Start the docker container
`docker run --detach --name vespa --hostname vespa-container
  --publish 8080:8080 --publish 19071:19071
  vespaengine/vespa`
- Move to the project directory and deploy the app
`vespa deploy --wait 300`
- Feed the documents
`vespa feed ext/1.json`
- Successful feed will show up as `"200": <number_of_documents>`

