# Forward port
`ssh -R 0.0.0.0:5566:localhost:5566 -N root@abc.com`

# Configure nginx on server
```
  location ~ ^/abc/(.*) {
    proxy_pass http://127.0.0.1:5566/$1;
    proxy_set_header Host ssp.otm-r.com;
  }
```

# Run
`docker-compose up`
