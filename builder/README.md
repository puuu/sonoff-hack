
Build docker image:
```console
sonoff-hack$ sudo docker build builder -t sonoff-hack
```

```console
sonoff-hack$ sudo docker run --rm -u $(id -u) -v $(pwd):/build sonoff-hack scripts/compile.sh
sonoff-hack$ sudo docker run --rm -u $(id -u) -v $(pwd):/build sonoff-hack fakeroot scripts/pack_fw.all.sh
```
