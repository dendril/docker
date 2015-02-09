
# Steps

1- clone the repo
1- go to folder `backstopjs`
1- `sudo docker build -t <your-username>/backstopjs .`
1- `sudo docker run -i -p 3001:3001 -t <your-username>/backstopjs /bin/bash`
1- `gulp reference`
1- `gulp test`
1- Check http://localhost:3001/compare/
