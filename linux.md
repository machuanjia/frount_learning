# linux 穿件用户 并对用户文件夹授权
```
chown -R machuanjia:machuanjia /home/machuanjia
chmod -R 775 /home/machuanjia

```

# git clone 改变权限，文件标记为修改
```
git config --add core.filemode false

在我没有改动服务器代码的情况下，使用git status经常看到大量文件有被修改的记录： git status 提示 old mode 100644 new mode 100755 原来是filemode的变化，文件chmod后其文件某些位是改变了的，但代码本身的内容有没有被改动。 使用git 命令 git config --add core.filemode false 忽略掉chmod改动

```