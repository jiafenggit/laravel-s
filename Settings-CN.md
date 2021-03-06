# LaravelS 配置项

- `listen_ip`：`string` 监听的IP，监听本机`127.0.0.1`(IPv4) `::1`(IPv6)，监听所有地址 `0.0.0.0`(IPv4) `::`(IPv6)， 默认`127.0.0.1`。

- `listen_port`：`int` 监听的端口，如果端口小于1024则需要`root`权限，default `5200`。

- `enable_gzip`：`bool` 当通过LaravelS响应数据时，是否启用gzip压缩响应的内容，依赖于库[zlib](https://zlib.net/)，通过命令`php --ri swoole|grep zlib`查看gzip是否可用。如果开启则会自动加上头部`Content-Encoding`，默认`false`，推荐开启gzip，会更省网络流量。

- `server`：`string` 当通过LaravelS响应数据时，设置HTTP头部`Server`的值，若为空则不设置，default `LaravelS`。

- `handle_static`：`bool` 是否开启LaravelS处理静态资源(要求 `Swoole >= 1.7.21`，若`Swoole >= 1.9.17`则由Swoole自己处理)，默认`false`，建议Nginx处理静态资源，LaravelS仅处理动态资源。静态资源的默认路径为`base_path('public')`，可通过修改`swoole.document_root`变更。

- `swoole`：`array` 请参考[Swoole配置项](https://wiki.swoole.com/wiki/page/274.html)