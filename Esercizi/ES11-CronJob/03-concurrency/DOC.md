

```sh

# tutti i metadati del cronjob
oc describe cronjob cronjob-simple

# estrarre solo gli eventi
oc describe cronjob cronjob-simple | awk '/Events:/,0'

# watch
# apt-get install -y procps
watch -n 5 "oc describe cronjob concurrency-allow -n prj-antonio-minelli | awk '/Events:/,0'"
watch -n 5 "oc describe cronjob concurrency-forbid -n prj-antonio-minelli | awk '/Events:/,0'"
watch -n 5 "oc describe cronjob concurrency-replace -n prj-antonio-minelli | awk '/Events:/,0'"

```