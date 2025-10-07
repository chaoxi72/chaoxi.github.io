### docker命令
- 将docker容器打包成镜像
```bash
docker commit <容器ID或名称> <新镜像名>:<标签>
docker commit -a <作者> -m <说明> <容器ID或名称> <新镜像名>:<标签>
```
- 导出镜像文件
```bash
docker save -o <压缩文件名> <新镜像名>:<标签>
```