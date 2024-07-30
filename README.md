# SRA Jumpoint Docker Cluster Node Via API

## Prerequisites
1. Create a jumpoint which is linux clustered and set it up with appropriate users etc. and save the code_name
2. Create an API account with "Allow Access" for the Configuration API and save the id and secret
3. Use the site's hostname, id, secret and jumpoint code_name to proceed in launching the docker jumpoint

## Methods to getting it running
### Use the public image on docker.io
```
docker run  -e BT_API_HOST=<hostname ex: example.com> -e BT_CLIENT_ID=<beyondtrust site api id> -e BT_CLIENT_SECRET=<beyondtrust site api secret> -e BT_JP_CODE_NAME=<code_name of your created jumpoint> allenmcgehee/sra-jpt-api
```

### Building an image and running it:
In this directory run:
```
docker build . --tag 'bt-jpt-api'
docker run  -e BT_API_HOST=<hostname ex: example.com> -e BT_CLIENT_ID=<beyondtrust site api id> -e BT_CLIENT_SECRET=<beyondtrust site api secret> -e BT_JP_CODE_NAME=<code_name of your created jumpoint> 'bt-jpt-api'
```

### Docker compose
In this directory run:
```
BT_API_HOST=<hostname ex: example.com> BT_CLIENT_ID=<beyondtrust site api id> BT_CLIENT_SECRET=<beyondtrust site api secret> BT_JP_CODE_NAME=<code_name of your created jumpoint>  docker compose up
```