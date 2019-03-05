# sublime-text3 plug-in
推荐比较好用的sublime-text插件，内附安装及使用方法（系统：windows）

## 安装Package Control
执行ctrl+`，在编辑器底部打开输入框，然后粘贴下面的语法，回车。
(```)
  import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
(```)

## Terminal
在编辑器左侧的目录上直接鼠标右键即可执行git bash的命令，并且打开的路径为所选文件的路径

安装步骤：
  1. 打开 Preferences>Package Control，选择Install Package
  2. 在搜索框输入Terminal，在搜索结果里点击Terminal 安装
  3. 打开 Preferences > Package setting > Terminal > Setting - User
  4. 更改文件配置：
    (```)
      {
        // git安装的路径
        "terminal": "C:\\Program Files\\Git\\git-bash.exe",
        "parameters": ["-c", "cd \"%CWD%\" && \"C:\\Program Files\\Git\\bin\\sh.exe\" -i -l"]
      }
    (```)
  5. 重启Sublime Text3
  6. 打开 Preferences > Key Bindings，修改冲突的快捷键
    [
      // 重新打开页面
      { "keys": ["ctrl+shift+t"], "command": "reopen_last_file" },
    ]

说明：因为ctrl+shift+t快捷键是打开最近关闭文件的默认快捷键，与Terminal的快捷键冲突，而且我一般习惯鼠标右键执行git-bash，所以需要重新设置一下快捷键。
