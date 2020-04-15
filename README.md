* 功能

> 用 redis DUMP+RESTORE 来序列化信息

> 提供一个方便上传信息的微服务

> 后续看要怎么嫁接前端（pending）

* 数据结构

> 采用 redis 的hashmap，每一个 hashmap 对应一笔资料（看作 transaction）

> 每一笔资料包含 id (key) \ title \ url \ timestamp \ tagcode

> tagcode 采用质数 modulus 方式编码，对照表参考 modulus 这笔 hashmap

* 使用

> 启动 redis-cli

> 安装 roswell

> ros build gatekeeper.ros

> 启动 gatekeeper （默 9000 端口，用-p 改）

> gatekeeper 会自动 RESTORE /data 里面的序列化信息

> POST add 更新清单

> GET save 保存当前变更

* 后续

> 把 gatekeeper 事先 build 好（ubuntu/centos/osx/windows），放到/builds

> 加个 merge 来把 db 重叠

* 备注

> 用我的 git 里面的 clack，有做没 merge 的更动
