## 使用git在多台机器上同步sublime text的设置和插件

### [](https://github.com/zxishere/st3#package文件夹位置)package文件夹位置

windows: `C:\Users\[YourName]\AppData\Roaming\Sublime Text 3\Packages` mac: `/Library/Application\ Support/Sublime\ Text\ 3/Packages/`

如果是windows下安装的是便携版，则为自定义路径，如:`D:\Program Files\Sublime Text Build 3083 x64\Data\Packages\User`

有些文件/文件夹不需要同步，加入到.gitignore

``` shell
Package Control.last-run
Package Control.ca-list
Package Control.ca-bundle
Package Control.system-ca-bundle
Package Control.cache/
Package Control.ca-certs/
```

在第一台电脑上

``` shell
cd [package folder]/User/
git init
git add
git commit -m "Initial"
git remote add origin [your git repo]
git push origin master
```

### [](https://github.com/zxishere/st3#这样就可以在其他电脑上clone这个repo了)这样就可以在其他电脑上clone这个repo了

``` shell
cd [package folder]
mv User User.old
git clone [your git repo] User
```

### [](https://github.com/zxishere/st3#如果设置有了改变再同步到repo里)如果设置有了改变，再同步到repo里

``` shell
cd [package folder]/User
git add -A
git commit -m "Update settings"
git push
```

### [](https://github.com/zxishere/st3#在其他电脑上同步)在其他电脑上同步

``` shell
cd [package folder]/User
git pull
```

