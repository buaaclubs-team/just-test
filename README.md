# just-test
用于测试团队开发功能

### 用法：

> git clone  git clone https://github.com/buaaclubs-team/just-test.git  
> cd just-test  
> 进行你的修改...  
> git push -u origin master #提交你的修改  

如果可以正常提交，则说明在你上一次与github远程代码库同步之后，中间没有修改。
如果有修改，提交会失败，先让你进行git pull，下载远程代码并与当前分支（可以指定分支）合并；使用git fetch只下载远程代码，不合并，自己通过git merge合并
如果代码merge成功（两份代码的所有修改没有冲突——没有同时修改一块代码的情况），不会有任何错误，继续git push即可
如果代码merge失败，说明有冲突
冲突的处理：
git status可以看到冲突的文件名
一一进入每个冲突文件，冲突位置处会有如下格式内容：

>  <<<<<<<Head  
>  当前分支内容  
>  =======   
>  被合并分支内容  

> \>>>>>origin/master

将这块代码修改为正确的代码（二者选择保留或结合保留）。PS：及时你不做任何更改，直接commit -a，git会认为你已经完成冲突合并
然后git commit -a，不需要-m添加附注，此时git认为你已经完成合并。完成合并后会出现一个合并处理过程的回顾说明，按ctrl-x退出，git至此退出merge冲突装填，回到正常状态

再次git push -u origin master即可提交分支

这是一个简要的说明，以上操作过程在服务器端实现，PC端的git大家自己探索一下，应该是类似的
