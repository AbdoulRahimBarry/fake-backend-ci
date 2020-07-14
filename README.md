# fake-backend-ci from deve
docker run --name NomContainer -p 80:5000(port expose en 80) -v {PWD}/student-list.json:data/student-list.json -d NomImage:Tags
