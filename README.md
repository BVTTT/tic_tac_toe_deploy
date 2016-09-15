# Tic Tac Toe App deployment

## Dependencies

- docker
- docker-compose
- docker-machine
- git-secret

## Steps

Decrypt secrets

```
git secrets reveal
```

Create docker machine
```
./create_machine # will attempt to create an aws ec2 instance
# .... lots of waiting

docker-compose up -d
```

# For debugging purposes

You should be able to run

```
docker-machine create # Create a local machine
eval $(docker-machine env) # expose docker variables
echo "api.ticstacstoes.com  $(docker-machine ip)" >> /etc/hosts
echo "ui.ticstacstoes.com  $(docker-machine ip)" >> /etc/hosts

docker-compose up -d

open http://ui.tictacstoes.com # Open ui app
```


