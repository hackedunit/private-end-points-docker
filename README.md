
# ENVIRONMENT VARIABLES

ENCRYPTME_USER
ENCRYPTME_PASSWORD
ENCRYPTME_TARGET_ID
ENCRYPTME_SERVER_NAME

These are required on first run only, if you wish to automate registration.

You can bootstrap interactively if you run with a tty:

    docker build -t encryptme .
    docker run -it --rm -v `pwd`/runconf:/etc/encryptme \
      --privileged \
      --net host \
      encryptme


# MOUNTPOINTS

  /etc/encyptme

  Location where config, certs, keys are stored.  These need to be kept
  across container restarts.


### TODO:


- Determine whether to add 10.x.x.x rule and -j REJECT

- Get strongswan running and document required args for docker
  https://github.com/philpl/docker-strongswan
- Integrate Letsencrypt (including ipsec.conf)
- Use supervisord
- Make update-pki.sh use supervisor restarts

