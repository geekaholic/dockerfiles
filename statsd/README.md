# Docker statsD

Simple statsD server running on UDP 8125. Might be useful for debugging that statsd clients are sending data correctly.

```
$ docker run --rm -p 8125:8125/udp -it geekaholic/statsd
```

To test...

```
# echo echo "foo:1|c" | nc -w 1 -u 127.0.0.1 8125
```
