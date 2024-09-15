# Python pip安装lxml报错的解决方案
## 问题描述
使用pip安装lxml时，可能会引发报错
``` bash
pip install lxml
```
报错内容
```
Building wheels for collected packages: lxml
  Building wheel for lxml (pyproject.toml) ... error
  error: subprocess-exited-with-error

  × Building wheel for lxml (pyproject.toml) did not run successfully.
  │ exit code: 1
  ╰─> [75 lines of output]
      <string>:57: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
      Building lxml version 3.8.0.
      Building without Cython.
      ERROR: b"'xslt-config' \xb2\xbb\xca\xc7\xc4\xda\xb2\xbf\xbb\xf2\xcd\xe2\xb2\xbf\xc3\xfc\xc1\xee\xa3\xac\xd2\xb2\xb2\xbb\xca\xc7\xbf\xc9\xd4\xcb\xd0\xd0\xb5\xc4\xb3\xcc\xd0\xf2\r\n\xbb\xf2\xc5\xfa\xb4\xa6\xc0\xed\xce\xc4\xbc\xfe\xa1\xa3\r\n"
      ** make sure the development packages of libxml2 and libxslt are installed **

      Using build configuration of libxslt
      running bdist_wheel
      running build
      running build_py
      creating build
      creating build\lib.win-amd64-cpython-39
      creating build\lib.win-amd64-cpython-39\lxml
      copying src\lxml\builder.py -> build\lib.win-amd64-cpython-39\lxml

......

      copying src\lxml\isoschematron\resources\xsl\iso-schematron-xslt1\readme.txt -> build\lib.win-amd64-cpython-39\lxml\isoschematron\resources\xsl\iso-schematron-xslt1
      running build_ext
      building 'lxml.etree' extension
      error: Microsoft Visual C++ 14.0 or greater is required. Get it with "Microsoft C++ Build Tools": https://visualstudio.microsoft.com/visual-cpp-build-tools/
      [end of output]

  note: This error originates from a subprocess, and is likely not a problem with pip.
  ERROR: Failed building wheel for lxml
Failed to build lxml
ERROR: Could not build wheels for lxml, which is required to install pyproject.toml-based projects
```
即使换源也无法结果问题
-------------------------------------------------
## 解决方案
- 安装 wheel
  ``` bash
  pip install wheel
  ```
- 到[pypi官网](https://pypi.org/project/lxml/#files)去下载对应版本的.whl文件
  我系统是Windows，Python版本3.9，就下载lxml-5.3.0-cp39-cp39-win_amd64.whl这个.whl文件
- cd到该.whl文件所在的文件夹，输入
  ``` bash
  pip install 带后缀的完整文件名
  ```
  若没有报错，则安装成功
