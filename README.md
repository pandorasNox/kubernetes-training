
kubectl port-forward nginx-deployment-59f5bbbdfb-dmmvk 8080:80
=> [::1]:8080

curl --resolve foo.bar.com:80:172.17.8.101 http://foo.bar.com/foo

- wordpress php-fpm
    - https://github.com/docker-library/wordpress/issues/250
