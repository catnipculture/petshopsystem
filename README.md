> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

本系统分为管理员、用户两个角色

管理员的主要功能：在后台主要管理收货地址管理、购物车管理、商品管理、商品收藏管理、商品评价管理、商品订单管理、字典管理、公告管理、用户管理、管理员管理等。

用户的主要功能：可以在首页查看宠物的资讯信息，可以查看商品信息，并加入购物车进行购买，在用户的个人中心查看和修改个人信息

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

前端：vue

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)



# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/20df3e8c44ace2b5adb03b6652c7449d.png)

### 项目截图

前台

![318基于ssm的萌宠宜家商城系统pf4](https://i-blog.csdnimg.cn/img_convert/6a29cd2f6966494793779bfa543765fb.png)

![318基于ssm的萌宠宜家商城系统pf5](https://i-blog.csdnimg.cn/img_convert/91e5ff38ff359b7e2640dc7a85e6d6e8.png)

![318基于ssm的萌宠宜家商城系统pf6](https://i-blog.csdnimg.cn/img_convert/815b42e2a2d97fac7d285970a005d63f.png)

后台

![318基于ssm的萌宠宜家商城系统pf1](https://i-blog.csdnimg.cn/img_convert/063eb50e5722f5390eab6f29a8d72777.png)

![318基于ssm的萌宠宜家商城系统pf2](https://i-blog.csdnimg.cn/img_convert/0d2939ba63207b2398b3d72316e91377.png)

![318基于ssm的萌宠宜家商城系统pf3](https://i-blog.csdnimg.cn/img_convert/0c9a0ce1fffab7bcfde7fb57bea0ea65.png)
### 代码

```
   //查询生活区的租户
            CustomerDO customerDO = customerMapper.selectOne(new LambdaQueryWrapper<CustomerDO>().eq(CustomerDO::getTelephone, RequestUtils.getCurrentUserPhone()));
            if (customerDO != null){
                List<TenantVO> lifeTenantList = getLifeTenantList(customerDO.getId());
                userVO.setLifeTenantList(lifeTenantList);
                if (CollectionUtils.isNotEmpty(lifeTenantList)){
                    tenantList.addAll(lifeTenantList);
                }
            }
            if (CollectionUtils.isNotEmpty(tenantList)){
                tenantList = tenantList.stream().distinct().collect(Collectors.toList());
            }
            userVO.setTenantList(tenantList);
            userVO.setTenantId(RequestUtils.getCurrentTenantId());
            userVO.setTenantAdmin(isTenantAdmin());
            userVO.setOrgNames(getCurrentOrganizationByUserId(user.getId()));
```
