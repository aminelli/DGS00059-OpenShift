

```sh

# tutti i metadati del cronjob
oc describe cronjob cronjob-simple

# estrarre solo gli eventi
oc describe cronjob cronjob-simple | awk '/Events:/,0'

```