## 环境变量
- WSL和Windows的环境变量隔离
```shell
  sudo vim /etc/wsl.conf
```
```shell
[interop]
appendWindowsPath = false
enabled = false
```
- appendWindowsPath = false：阻止将 Windows 的 PATH 添加到 WSL 的 PATH 中
- enabled = false：完全禁用 Windows 互操作性（会阻止运行 Windows 程序）

## SSH
- 对于wsl的ssh连接，使用xshell连接wsl时，会出现连接不上
  - 需要使用windows转发wsl的接口
  ```bash
  netsh interface portproxy add v4tov4 listenport=2222 listenaddress=0.0.0.0 connectport=22 connectaddress=127.0.0.1
  ```
  - 查看映射端口
  ```bash
  netsh interface portproxy show all
  ``` 
  - 关闭映射端口
  ```bash
  netsh interface portproxy delete v4tov4 listenport=2222 listenaddress=0.0.0.0
  ``` 
