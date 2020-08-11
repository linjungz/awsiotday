## Lab0:创建新用户


登录AWS Account的账号，在服务界面输入IAM并点击进入。
![](../md_images/create_user_0.png)

在左侧展开访问管理，选择“用户”， 然后点击“添加用户”
![](../md_images/create_user_1.png)

输入用户名：kvs-demo, 勾选“编程访问”
![](../md_images/create_user_2.png)

这里选择“直接附加现有策略”，搜索策略名称“kinesisvideo”勾选“AdminKinesisVideoStreamsFullAccess”这个策略。
![](../md_images/create_user_3.png)

不做处理点击“审核”
![](../md_images/create_user_4.png)

点击“创建用户”
![](../md_images/create_user_5.png)

务必点击“下载”
![](../md_images/create_user_6.png)

新用户kvs-demo创建完成。
