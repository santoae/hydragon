These repository is for dockerfiles that create a node for Hydragon testnet of Hydrachain.


<BASE>

To run the image : docker run -it --name < name > --restart unless-stopped -v $(cd ~/< local directory >&& pwd):/hydragon santoae/hydragon-base
--replace < name > and < local directory > for your use case.

After running this container the configurations files will be in out < local directory >

<NODE>

To run the image : docker run -it -p 1478:1478 -p 8545:8545 -p 9632:9632 --name < name > --restart unless-stopped -v $(cd ~/< local directory >&& pwd):/hydragon santoae/hydragon-node
--replace < name > and < local directory > for your use case.

Interactive mode is needed to put the password (for now). Leave the container running with ctrl-p + crtl-q
