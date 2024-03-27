## Git基础命令学习

1.git init：创建仓库

2.pwd：查看当前仓库

3.git add ：将文件添加到暂存区

​	例：git add sipsg-city-lifeline-all-data-service.jar sipsg-city-lifeline-all-data-service.jar.original

​	add后是提交的文件名。

4.git commit：把文件提交到仓库。

​	例：git commit -m "zhgd提交"

​	"zhgd提交"这是提交的注释

5.git status：查看是否还有文件未提交。

6.git log：查看历史记录

​	git log –pretty=oneline ：比较简洁的历史记录

7.git reset --hard HEAD^：操作回退到上一个版本

​	git reset --hard HEAD^^：操作回退两个版本，以此类推

8.cat readme.txt：可以用来查看txt的内容。

9.git reflog ：查看操作的版本号。

​	配合：git reset --hard版本号 ：实现指定版本退回操作

​	示例：![img](https://pic4.zhimg.com/v2-d5fcbdd6c68e194c470b60cf7e4c8353_r.jpg)

​		  ![img](https://pic3.zhimg.com/v2-b8b391807ab7b5726bd017db8f03fd26_r.jpg)

10.rm 文件名：删除该文件

11.git checkout -- file：撤销修改（有点抽象，修改，添加到暂存区，提交。三个步骤的区别）

```java
//以上都是仓库的一些命令-----------------------------------------------以下是远程仓库的步骤-----------
```

第一步：创建SSH Key ：ssh-keygen -t rsa –C “youremail@example.com”

​		id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

![1711520587345](C:\Users\os10\AppData\Roaming\Typora\typora-user-images\1711520587345.png)

第二步：github-->settings-->SSH Keys-->Add SSHkey。在Key文本框里黏贴id_rsa.pub文件的内容。

现在的情景是：我们已经在本地创建了一个Git仓库后，又想在github创建一个Git仓库，并且希望这两个仓库进行远程同步，这样github的仓库可以作为备份，又可以其他人通过该仓库来协作。

第三步：github-->create a new repo

![1711521037131](C:\Users\os10\AppData\Roaming\Typora\typora-user-images\1711521037131.png)

GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

根据提示来执行代码

第四步：git remote add origin https://github.com/xiaoyiyayaya/zhgd.git
​		git branch -M main
​		git push -u origin main
若是没有执行git branch -M main（将分支转换为主支）
则执行 git push -u origin master

![1711521795988](C:\Users\os10\AppData\Roaming\Typora\typora-user-images\1711521795988.png)

完成后就可以在github上看到自己提交的东西了

![1711522116752](C:\Users\os10\AppData\Roaming\Typora\typora-user-images\1711522116752.png)

现在开始，只要本地做了提交 就可以通过git push origin master（main）将本地最新修改推送到github上了

git commit
git push origin master（main）