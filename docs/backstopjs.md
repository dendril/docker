
# Steps

1. `git clone <this-repo>`
2. `cd <this-repo>/backstopjs`
3. `sudo docker build -t <your-username>/backstopjs .`
4. `sudo docker run -i -p 3001:3001 -t <your-username>/backstopjs /bin/bash`
5. `gulp reference` this is only required the first time for create the reference database
6. `gulp test` test against the reference database
7. See the results in the [report section](http://localhost:3001/compare/)
