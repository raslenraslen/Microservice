# Microservice


`````bash
git pull --rebase origin adservice
git add <fichier_conflit>
git rebase --continue
git push -u origin adservice

``````


### install ngrok for Jenkins

`````` bash
curl -sSL https://ngrok-agent.s3.amazonaws.com/ngrok.asc \
  | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null \
  && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" \
  | sudo tee /etc/apt/sources.list.d/ngrok.list \
  && sudo apt update \
  && sudo apt install ngrok

``````
then run 

````
ngrok config add-authtoken <token>
ngrok http 8080
