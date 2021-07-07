# Build
```bash
$ cd hello-world-site

# This is the local tag
$ docker build . --tag=$(basename $(pwd)):git-$(git rev-parse --short HEAD)

# Make it the latest
$ docker tag hello-world-site:git-fe021cc alexhwoods/hello-world-site:latest

# Push to that repo
$ docker push alexhwoods/hello-world-site:latest
```

# Test
```bash
$ docker run -p 4000:80 alexhwoods/hello-world-site

# In another terminal
$ curl http://localhost:4000
<html>
  <head><meta charset="UTF-8">
    <title>Hello World</title>
  </head>
  <body>
      <p>Can I interest you in some 🥑?</p>
  </body>
</html>
```