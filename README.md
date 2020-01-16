# kcptun-sip003-wrapper
shadowsocks SIP003 wrapper for [xtaci/kcptun](https://github.com/xtaci/kcptun/releases/latest), work like [shadowsocks/kcptun](https://github.com/shadowsocks/kcptun/releases/tag/v20170718).

## Windows
1. Put kcptun binary in the same directory of this script or into a directory in the PATH environemnt.
   ### searching precedence
   - \`pwd\`/kcptun_client$suffix
   - \`pwd\`/kcptun-client$suffix
   - \`pwd\`/client_${os}_$arch$suffix
   - \`pwd\`/kcptun_server$suffix
   - \`pwd\`/kcptun-server$suffix
   - \`pwd\`/server_${os}_$arch$suffix
   - $PATH/kcptun_client$suffix
   - $PATH/kcptun-client$suffix
   - $PATH/kcptun_server$suffix
   - $PATH/kcptun-server$suffix

   ##### $suffix: in windows means .exe; in unix-like os means null/None/Empty String
## Posix system:
It's a bash script and will check all parameters from shadowsocks according the [xtaci/kcptun](https://github.com/xtaci/kcptun). And, it support almost all the paremeter valid for xtaci/kcptun.
1. Put this script in any location you want, make sure appropriate xtaci/kcptun binary is in $PATH or in the same dirctory with this script.
2. Rename this script or just make linker to kcptun.server | kcptun_server | kcptun-server | kcptun.client | kcptun_client | kcptun-client; or just specify "server" or "client" in plugin-opts from shadowsocks.

e.g.
server side:
ss-server --plugin "YOUR_LOCATION_OF_THIS_SCRIPT/kcptun" --plugin-opts "server;key=xxxx;crypt=xxxx;...." --ANY_OTHER_PAREMETERS
##### ln -s kcptun kcptun.server
ss-server --plugin "YOUR_LOCATION_OF_THIS_SCRIPT/kcptun.server" --plugin-opts "key=xxxx;crypt=xxxx;...." --ANY_OTHER_PAREMETERS
client side:
ss-local --plugin "YOUR_LOCATION_OF_THIS_SCRIPT/kcptun" --plugin-opts "client;key=xxxx;crypt=xxxx;...." --ANY_OTHER_PAREMETERS
##### ln -s kcptun kcptun.client
ss-local --plugin "YOUR_LOCATION_OF_THIS_SCRIPT/kcptun.client" --plugin-opts "key=xxxx;crypt=xxxx;...." --ANY_OTHER_PAREMETERS
