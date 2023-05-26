## github 和 gitlab 多个ssh账号问题

```
// 进入到ssh目录
cd ~/.ssh   
// github 公钥
cat id_rsa.pub 

// 生成gitlab ssh key ，名字叫id_rsa_gitlab
ssh-keygen -t rsa -C “邮箱名称@xxx.com” -f ~/.ssh/id_rsa_gitlab

// 配置config文件
Host github.com                                                                  
     HostName github.com                                                          
     PreferredAuthentications publickey                                           
     IdentityFile ~/.ssh/id_rsa                                           
                                                                                 
Host gitlab.yhroot.com                                                            
     HostName gitlab.yhroot.com                                                    
     PreferredAuthentications publickey                                           
     IdentityFile ~/.ssh/id_rsa_gitlab
 
// 将ssh key 配置到gitlab上
cat id_rsa_gitlab.pub 
复制到gitlab中的ssh

```
