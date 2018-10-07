# 打包一步骤（master分支）
```
# 全局安装electron
$ npm install electron -g

# 安装依赖
$ npm install

# 本地调试
$ npm start 

# 生成打包文件
$ npm run package

```
- 最终生成名为`lv6/lv6-win32-x64`的文件夹
- 打包完成需要去‘\resources\app‘ 下安装依赖包 `$ npm install getmac`


# 打包二步骤-生成exe文件（second分支）


1. 切换到second分支，并将lv6-win32-x64复制到其`/build`目录下面(与Gruntfile.js同级)

2. 再次需要去`\resources\app` 下删除node_modules（注意：每次移动过文件夹都需要重新删除node_modules），并重新安装依赖包$ npm install / $ npm install getmac只需要安装这一个就可以（不然就会报路径或者文件名过长的错误）。

3. 在`/build`中(包含Gruntfile.js) 进行npm install

4. 全局安装grunt，并在`/build`运行 `$ grunt`

5. 输出文件在`/dist`处

# 常见错误
- 此错误最为常见，字符超了，在我本地命令行可能报出来有问题。

`
Running "create-windows-installer:x64" (create-windows-installer) task
Warning: Failed with exit code: 1
Output:
Attempting to build package from 'orion.nuspec'.
The specified path, file name, or both are too long. The fully qualified file name must be less than 260 characters, and the directory name must be less than 248 characters.
 Use --force to continue.
`
