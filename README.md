# pelias

Docker-based pelias install based largely on https://github.com/helvalius/pelias-docker.

### First make some directories in the project root:

```
mkdir -p data/elasticsearch
mkdir -p data/whosonfirst/meta
mkdir -p data/geonames/data
```

### Start elasticsearch:

```
docker-compose build elasticsearch
docker-compose up -d elasticsearch
```

### Download whosonfirst:

```
docker-compose build whosonfirst
docker-compose up whosonfirst
```

It will exit when complete.

### Download geonames:

```
docker-compose build geonames
docker-compose up geonames
```

It will exit when complete.

### Import data:

```
docker-compose build pelias
docker-compose run --rm pelias /bin/bash
$ pelias schema create_index
$ pelias geonames import -m
$ pelias geonames import -i all
```

This will take a long time.
