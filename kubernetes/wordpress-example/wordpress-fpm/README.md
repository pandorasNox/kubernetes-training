1. create new nginx img local
    `docker build -t wordpress-fpm-nginx:1 ./docker/nginx/`

2. proxy docker-registry from kube cluster
    `kubectl port-forward -n registry registry-8455476d5-z2hvm 5000`

3. re-tag local image
    `docker tag wordpress-fpm-nginx:1 localhost:5000/wordpress-fpm-nginx:1`

4. push image to docker-reghistry
    `docker push localhost:5000/wordpress-fpm-nginx:1`

5. apply deplyo + service amd in deployment.yml use the right image
    `image: 10.16.0.5:5000/wordpress-fpm-nginx:1`
    `kubectl apply -f kubernetes/wordpress-example/wordpress-fpm/namespace.yml kubernetes/wordpress-example/wordpress-fpm/`
    check: `watch kubectl get pods`
