# Hydrachain Hydragon Testnet Docker Files

This repository contains Dockerfiles for creating and running a node for the Hydragon testnet of Hydrachain.

## Create a Node 
To create a Hydragon node, use the `hydragon-base` image.

### Run the Image
`docker run -it --name <name> -v $(cd ~/<local_directory> && pwd):/hydragon santoae/hydragon-base`

(replace < name > and < local directory > for your use case)

After running this container the configurations files will be in < local directory >

## Run a node 
To run a Hydragon node, use the `hydragon-node` image.

`docker run -it -p 1478:1478 -p 8545:8545 -p 9632:9632 --name < name > --restart unless-stopped -v $(cd ~/< local directory >&& pwd):/hydragon santoae/hydragon-node`

(replace < name > and < local directory > for your use case)

Interactive mode is needed to put the password (for now). Leave the container running with ctrl-p + crtl-q

##  Interact with your node 

`docker exec -it $(sudo docker ps|grep "hydragon-node" | awk '{print ($1)}') bash`

Check node status:
`docker exec $(sudo docker ps|grep "hydragon-node" | awk '{print ($1)}') hydragon-node/hydra status`
