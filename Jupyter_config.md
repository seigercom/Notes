## jupyter notebook 配置
安装好jupyter notebook 后运行可以本地访问，如果外网访问需要配置

* 生成配置文件

  `jupyter notebook --generate-config`

* 生成密码（如果需要）

  `jupyter notebook password`

* 修改配置

  在路径`~/.jupyter/`中，找到jupyter_notebook_config.py，修改

  ```
  c.NotebookApp.ip='0.0.0.0' #允许所有ip访问
  c.NotebookApp.password=u'sha:ce...'# 刚才生成的密钥，可以不用
  c.NotebookApp.open_browser=False
  c.NotebookApp.port=8888 #打开端口
  ```

   