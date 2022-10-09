docker-compose up -d # -d will start the containers in "detached" mode so they continue running after you close the shell

docker ps to see if everything is up and running

place autostart file here:
/etc/xdg/lxsession/LXDE-pi 


possible health checks
    healthcheck:
      test: "ln -sf /bin/busybox /bin/wget && /bin/wget -q -Y off http://localhost:8086/metrics -O /dev/null > /dev/null 2>&1"
      interval: 25s
      timeout: 3s
      start_period: 30s