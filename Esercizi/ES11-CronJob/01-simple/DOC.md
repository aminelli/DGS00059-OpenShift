

```sh

# tutti i metadati del cronjob
oc describe cronjob cronjob-simple

# estrarre solo gli eventi
oc describe cronjob cronjob-simple | awk '/Events:/,0'

# watch
# apt-get install -y procps
watch -n 5 "oc describe cronjob cronjob-simple | awk '/Events:/,0'"

```