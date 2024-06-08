# Github


### 关键字查询
   **awesome** ,去此标签类别中查询项目

   **python tutorial**, 查询资料，书籍，文档

   **socket sample**, 查询对应技术的代码样本


## github 三要素


### Repository 仓库

    仓库是github项目管理存储基本单位

    一个仓库中存储一个项目，一个用户可以拥有多个仓库，一般仓库分为public, private

### Commit 提交

    程序员在整个开发周期，有大量的对代码资源的迭代和修改，都可以通过commit的方式进行记录，以便于程序员回溯代码，即使这些代码被删除

    提交便于使用者观察整个工程的开发流程以及设计流程
    
### Branch 分支

    在仓库中可以包含多个分支，分支才是代码文件的第一存储单位，默认的仓库主分支为master/main

    * 不仅可以管理代码存储，便于多人协作开发

[![2024-06-07-222002.jpg](https://i.postimg.cc/132ccWLt/2024-06-07-222002.jpg)](https://postimg.cc/Hr0yTtWD)    


## 仓库内容

  **Code**,资源存储，代码资源，二进制，项目管理脚本，许可证等等
 
  **issues**,使用时遇到的bug或进行提交，等待反馈
 
  **README**,使用markdown语言编写，工程自述文件，开发进度，版本更新，使用介绍等等

  **LICENSE许可证**

  GPL2.0,3.0  Apahce2.0 Mit, 这些许可证，给使用者最大使用权限以及最少的限制


## Git软件，分布式版本布置系统
   仓库管理软件，使用git管理私人代码或企业代码

[![2024-06-07-224224.jpg](https://i.postimg.cc/8Pr086Nj/2024-06-07-224224.jpg)](https://postimg.cc/MvqDVXcS)


## 设备认证

### 1.如何让网站的账户与设备绑定，后续完成代码的管理
```bush
       git init //创建本地仓库    后续对仓库的操作，都要在仓库位置（master）
                               
       git config --list //查看git的配置文件

       git config --global user.email "邮箱“

       git config --global user.name "用户名"

       ssh-keygen -t rsa -C "注册邮箱" //创建本地密文
```
#### 去对应的目录查找密文文件
```bush
       rsa.pub 复制密文，粘贴 setting -> SSH key and GPD -> new ssh key -> 粘贴

       ssh -T git@github.com //测试关联是否成功   ssh远程登录
```
### 2.为目标仓库起别名，定位目标仓库，后续上传
```bush
       git remote add orgin "ssh地址" //为ssh仓库地址创建别名为origin

       git remote remove orgin //删除origin别名

       git remote add orgin "ssh地址" //为ssh仓库地址创建别名为origin
```

## 本地设备与云端仓库的交互逻辑

[![2024-06-08-085250.jpg](https://i.postimg.cc/zG8VLmRR/2024-06-08-085250.jpg)](https://postimg.cc/w746PG26)

```bush
       git add //添加内容

       git rm //删除本地文件并删除仓库数据

       git restroe //恢复被删除(仓库存在)
```
[![2024-06-08-090102.jpg](https://i.postimg.cc/50Y0cbDD/2024-06-08-090102.jpg)](https://postimg.cc/jwTKP0xh)

## 代码更新的依赖关系被破坏
   本地内容要比云端新，完成更新替换，但是如果直接修改云端内容，会导致本地内容无法再次提交

   *先拉取 git pull 云端内容 与本地内容合并操作，然后再次推即可（先拉再推）*

```bush
       git pull --rebase origin master

       git rebase --skip "忽略旧版，更新本地后可以上传"

       git rebase --abort "忽略新版，此时还不能上传"

       git rebase --continue "版本合并，解决冲突后可以直接上传"
```
[![2024-06-08-100121.jpg](https://i.postimg.cc/sfPB3DMR/2024-06-08-100121.jpg)](https://postimg.cc/mhDZw43d)

[![2024-06-08-100041.jpg](https://i.postimg.cc/QCqVmS2M/2024-06-08-100041.jpg)](https://postimg.cc/BPXqQ5QW)

[![2024-06-08-094231.jpg](https://i.postimg.cc/T1nn6rZ8/2024-06-08-094231.jpg)](https://postimg.cc/zHXywRzp)

[![2024-06-08-094555.jpg](https://i.postimg.cc/8kvRMSsy/2024-06-08-094555.jpg)](https://postimg.cc/BtqPfRTD)

[![2024-06-08-094753.jpg](https://i.postimg.cc/jdrzhF7R/2024-06-08-094753.jpg)](https://postimg.cc/vD3gYXhK)

## 下载开源代码

```bush
       git clone "https仓库地址" //下载开源项目code资源
```

## 分支Branch
   关于分支的相关命令，创建分支，选择分支，合并分支等等

# Markdown语言

github 可以编写readme, 文本修饰语言
   
Markdown ，文本修饰语言，用特殊符号修饰正文效果<br> 

## 标题修饰符\#
   修饰符与正文之间要有空格

# 标题修饰符 (一级标题)
## (二级标题）
### (三级标题)
#### (四级标题)
##### (五级标题)

## 正文内容
   
   输入正文内容，但是如果需要换行，用\<br\> 标签

## 修饰正文

*一段测试文本*

**一段测试文本**

***一段测试文本***

~~一段测试文本~~

这是一段测试文本，将`关键字`重点显示

## 分割线
  用\-\-\- 表示分割线
---

## 引用效用\>表示
> 煮豆燃豆萁，豆在釜中泣。本是同根生，相煎何太急。
>>曹丕
>>>魏国
>>>>三国演义

## 列表修饰符

### 无序列表 \*
* 单机游戏
  * 植物大战僵尸
    * 冰帝--寒冰高坚果
* MOBEL
  * 王者荣耀
  * 和平精英

### 有序列表 1.
1. 数学
   1. 几何
   2. 代数
2. 诗词
   1. 唐诗
   2. 宋词

### 混合列表
1. 一级测试
   * 测试二级
   2. 测试三级

### 表格
名称|职业|技能
--|:--:|--:
纳兹|灭龙魔导士|红莲爆炎刃
露西|星灵召唤师|开星座之门

### 代码片段

```c
    
     #include <stdio.h>

     int main(){

      printf("test \n");
      return 0;
      }
```
```cpp
      #include <iostream>
      using namespace std;
      int main(){
        
	cout<<"test \n"<<endl;
        return 0;

      }
```
```python
          import <os>
```

```bush
        echo "测试"
```
### 超链接技术
[Github](https://www.github.com"点击访问")

### 插入图片
[![1.jpg](https://i.postimg.cc/Dw834DPM/1.jpg)](https://postimg.cc/tsQMLBf3)
