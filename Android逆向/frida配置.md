#### 安装frida
- frida和frida-tools对应版本,[参考资料](https://bbs.kanxue.com/thread-280436.htm)
###### 问题
1. 安装失败
```python
 x Failed to build `frida==14.2.18`
  |-> The build backend returned an error
  `-> Call to `setuptools.build_meta:__legacy__.build_wheel` failed (exit code: 1)

      [stdout]
      running bdist_wheel
      running build
      running build_py
      creating build\lib.win-amd64-cpython-38\frida
      copying frida\core.py -> build\lib.win-amd64-cpython-38\frida
      copying frida\__init__.py -> build\lib.win-amd64-cpython-38\frida
      running build_ext
      looking for prebuilt extension in home directory, i.e. C:\Users\Administrator/frida-14.2.18-py3.8-win-amd64.egg
      prebuilt extension not found in home directory, will try downloading it
      querying pypi for available prebuilds

      [stderr]
      Traceback (most recent call last):
        File "<string>", line 101, in build_extension
      FileNotFoundError: [Errno 2] No such file or directory:
      'C:\\Users\\Administrator/frida-14.2.18-py3.8-win-amd64.egg'

      During handling of the above exception, another exception occurred:

      Traceback (most recent call last):
        File "<string>", line 11, in <module>
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\build_meta.py",
      line 434, in build_wheel
          return _build(['bdist_wheel'])
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\build_meta.py",
      line 425, in _build
          return self._build_with_temp_dir(
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\build_meta.py",
      line 406, in _build_with_temp_dir
          self.run_setup()
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\build_meta.py",
      line 521, in run_setup
          super().run_setup(setup_script=setup_script)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\build_meta.py",
      line 319, in run_setup
          exec(code, locals())
        File "<string>", line 155, in <module>
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\__init__.py",
      line 117, in setup
          return distutils.core.setup(**attrs)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\core.py",
      line 183, in setup
          return run_commands(dist)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\core.py",
      line 199, in run_commands
          dist.run_commands()
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\dist.py",
      line 954, in run_commands
          self.run_command(cmd)
        File "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\dist.py",
      line 999, in run_command
          super().run_command(command)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\dist.py",
      line 973, in run_command
          cmd_obj.run()
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\command\bdist_wheel.py",
      line 400, in run
          self.run_command("build")
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\cmd.py",
      line 316, in run_command
          self.distribution.run_command(command)
        File "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\dist.py",
      line 999, in run_command
          super().run_command(command)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\dist.py",
      line 973, in run_command
          cmd_obj.run()
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\command\build.py",
      line 135, in run
          self.run_command(cmd_name)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\cmd.py",
      line 316, in run_command
          self.distribution.run_command(command)
        File "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\dist.py",
      line 999, in run_command
          super().run_command(command)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\dist.py",
      line 973, in run_command
          cmd_obj.run()
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\command\build_ext.py",
      line 98, in run
          _build_ext.run(self)
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\command\build_ext.py",
      line 359, in run
          self.build_extensions()
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\command\build_ext.py",
      line 476, in build_extensions
          self._build_extensions_serial()
        File
      "C:\Users\Administrator\AppData\Local\uv\cache\builds-v0\.tmpik4owh\lib\site-packages\setuptools\_distutils\command\build_ext.py",
      line 502, in _build_extensions_serial
          self.build_extension(ext)
        File "<string>", line 108, in build_extension
        File "C:\Users\Administrator\AppData\Roaming\uv\python\cpython-3.8.20-windows-x86_64-none\lib\xmlrpc\client.py",
      line 1109, in __call__
          return self.__send(self.__name, args)
        File "C:\Users\Administrator\AppData\Roaming\uv\python\cpython-3.8.20-windows-x86_64-none\lib\xmlrpc\client.py",
      line 1450, in __request
          response = self.__transport.request(
        File "<string>", line 58, in request
        File "C:\Users\Administrator\AppData\Roaming\uv\python\cpython-3.8.20-windows-x86_64-none\lib\xmlrpc\client.py",
      line 1341, in parse_response
          return u.close()
        File "C:\Users\Administrator\AppData\Roaming\uv\python\cpython-3.8.20-windows-x86_64-none\lib\xmlrpc\client.py",
      line 655, in close
          raise Fault(**self._stack[0])
      xmlrpc.client.Fault: <Fault -32500: 'RuntimeError: PyPI no longer supports the XMLRPC package_releases method.
      Use JSON or Simple API instead. See https://warehouse.pypa.io/api-reference/xml-rpc.html#deprecated-methods for
      more information.'>

      hint: This usually indicates a problem with the package or the build environment.
```
解决方案: 
旧版的 frida Python 包（14.2.18） 在构建时会用 PyPI 的 XML-RPC 接口 查询预编译文件，
但 PyPI 已经在 2023 年彻底关闭了 XML-RPC 接口。
最新版（frida==16.x）已经兼容现代 PyPI API，不会再触发这个错误。
2. frida --version失败
```python
Traceback (most recent call last):
  File "C:\Users\Administrator\AppData\Roaming\uv\python\cpython-3.8.20-windows-x86_64-none\lib\runpy.py", line 194, in _run_module_as_main
    return _run_code(code, main_globals, None,
  File "C:\Users\Administrator\AppData\Roaming\uv\python\cpython-3.8.20-windows-x86_64-none\lib\runpy.py", line 87, in _run_code
    exec(code, run_globals)
  File "E:\Python\Frida\.venv\Scripts\frida.exe\__main__.py", line 4, in <module>
  File "E:\Python\Frida\.venv\lib\site-packages\frida_tools\repl.py", line 31, in <module>
    from frida_tools.application import ConsoleApplication
  File "E:\Python\Frida\.venv\lib\site-packages\frida_tools\application.py", line 17, in <module>
    import _frida
ModuleNotFoundError: No module named '_frida'
```
暂时猜测是因为frida和frida-tools版本对不上，直接使用上面链接中对应版本安装的，失败
失败版本
```bash
frida==16.7.18
frida-tools==12.0.4
```
成功版本
```bash
frida==16.2.1
frida-tools==12.3.0
```
#### frida-server安装
- 设备
  - pixel 6
- 系统
  - Android 14
- frida
  - 16.3.3
- frida-tools
  - 13.6.1
###### Server问题
1. 安装高版本的frida-server(16.5.2)，会使手机黑屏
原因：原因和下面问题2一致
解决方案：
```bash
pm uninstall com.google.android.art
重启设备
```
2. 安装低版本的frida-server(16.2.1, 16.3.3)，无法启动frida-server
```bash
{"type":"error","description":"TypeError: t is not a function","stack":"TypeError: t is not a function\n    at frida/node_modules/frida-java-bridge/lib/android.js:1591:1\n    at frida/node_modules/frida-java-bridge/lib/class-model.js:113:1\n    at CallbackContext.kt (frida/node_modules/frida-java-bridge/lib/android.js:586:1)\n    at NativeFunction.<anonymous> (<anonymous>)\n    at bt (frida/node_modules/frida-java-bridge/lib/android.js:577:1)\n    at frida/node_modules/frida-java-bridge/lib/class-model.js:112:1\n    at Function.build (frida/node_modules/frida-java-bridge/lib/class-model.js:7:1)\n    at k._make (frida/node_modules/frida-java-bridge/lib/class-factory.js:168:1)\n    at k.use (frida/node_modules/frida-java-bridge/lib/class-factory.js:62:1)\n    at frida/node_modules/frida-java-bridge/index.js:224:1","fileName":"frida/node_modules/frida-java-bridge/lib/android.js","lineNumber":1591,"columnNumber":1}
{"type":"error","description":"TypeError: Cannot read properties of undefined (reading 'find')","stack":"TypeError: Cannot read properties of undefined (reading 'find')\n    at F.value (frida/node_modules/frida-java-bridge/lib/class-factory.js:1018:1)\n    at F.value (frida/node_modules/frida-java-bridge/lib/class-factory.js:1034:1)\n    at Object.get (frida/node_modules/frida-java-bridge/lib/class-factory.js:746:1)\n    at frida/node_modules/frida-java-bridge/index.js:224:1\n    at c.perform (frida/node_modules/frida-java-bridge/lib/vm.js:12:1)\n    at _performPendingVmOpsWhenReady (frida/node_modules/frida-java-bridge/index.js:223:1)\n    at _.perform (frida/node_modules/frida-java-bridge/index.js:204:1)\n    at /internal-agent.js:490:6","fileName":"frida/node_modules/frida-java-bridge/lib/class-factory.js","lineNumber":1018,"columnNumber":1}
```
解决方案:
```bash
pm uninstall com.google.android.art
重启设备
```
参考文档:
[Latest Google Play System Update ruins Frida](https://github.com/frida/frida/issues/2958)
[bug in function instrumentArtMethodInvocationFromInterpreter](https://github.com/frida/frida-java-bridge/issues/309)
[Android Server; n is not a function, unable to perform state transition](https://github.com/frida/frida/issues/2037#issuecomment-2317730036)

以上两个问题猜测，frida-server安装失败或者执行失败和Android的art有关
