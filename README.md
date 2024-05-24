```
 echo -ne $(bitcoin-cli 54e48e5f5c656b26c3bca14a8c95aa583d07ebe84dde3b7dd4a78f4e4186e713 false 00000000000000ecbbff6bafb7efa2f7df05b227d5c73dca8f2635af32a2e949  | sed 's/0100000000000000/\n/g' | tail -n +2 | cut -c7-136,139-268,271-400 | tr -d '\n' | cut -c17-368600 | sed -e 's/../\\x&/g') > wp.pdf
```

Or, when running your node from a non-standard location, with `cd /path/to/bitcoin/folder`:

```
 echo -ne $(./bin/bitcoin-cli -datadir=./ getrawtransaction 54e48e5f5c656b26c3bca14a8c95aa583d07ebe84dde3b7dd4a78f4e4186e713 false 00000000000000ecbbff6bafb7efa2f7df05b227d5c73dca8f2635af32a2e949  | sed 's/0100000000000000/\n/g' | tail -n +2 | cut -c7-136,139-268,271-400 | tr -d '\n' | cut -c17-368600 | sed -e 's/../\\x&/g') > wp.pdf
 ```

```
sha256sum ./wp.pdf
```

Should yield `b1674191a88ec5cdd733e4240a81803105dc412d6c6708d53ab94fc248f4f553`
