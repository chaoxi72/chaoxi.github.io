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
