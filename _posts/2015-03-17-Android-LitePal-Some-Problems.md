---
layout: default
title: Android开发中的LitePal使用总结
---

# Android开发中的LitePal使用总结

### 1. LitePal简介

[**LitePal开源地址**](https://github.com/LitePalFramework/LitePal )
LitePal是一个开源的Android库，让开发人员更加方便地使用SQLite数据库。你可以完成大部分的数据库操作，而无需编写SQL语句，包括建立或升级表，CRUD（增删改查）操作，聚合函数等。LitePal的设置相当简单，你可以在不到5分钟时间内将它集成到你的项目中。

在LitePal开源地址的README文件中你可以找到使用说明。如果你的英文能力有限，可以看[郭霖的博客](http://blog.csdn.net/guolin_blog/article/details/38083103)，其中有几篇博文详细地介绍了LitePal的使用。

还有一分精简版的中文[LitePal使用](http://seniorzhai.github.io/2015/02/02/LitePal%E7%9A%84%E4%BD%BF%E7%94%A8/)，作者写的也很详细，适用于新手快速掌握LitePal的使用。

### 2. LitePal使用中的需要注意的几个问题
**1. 更改某个数据为默认值**
 
当需要将某个数据改为为默认值时，例如一个phone对象，其power属性为boolean类型，默认值是`false`，当你在某个方法中需要更改该属性为`false`，不能使用`phone.setPower(false)`,而是调用`setToDefault()`方法。用法也很简单，在`setToDefault()`方法中传入要修改的字段名就可以了(类中的字段名)。

默认值就是java中的基本数据类型的默认值，例如int类型的就是0，boolean类型的就是false

	<java>
		// phone.setPower(false);
		phone.setToDefault("power");
	</java>
	
**2. 查询boolean类型的字段时的问题**

boolean类型的字段在设置为真时就是是赋值`true`,以及使用`setToDefault()`方法，赋值都是`true`或`false`，但是实际存储时，存在数据库的为`1`或`0`，所以查询时查询参数应该为`1`和`0`，而不是`true`和`false`。还是以查询Phone表为例子，查找所有没电的手机，即`phone.isPower()==false`。  

	<java>
		// 错误的写法
		// List<Phone> noPowerPhones = DataSupport.where("power = ?", “false”).find(Phone.class);
		// 正确的写法
		List<Phone> noPowerPhones = DataSupport.where("power = ?", “0”).find(Phone.class);
	</java>
	
**3. 关联表新增关联项问题**

LitePal配置表关联很便捷，但在关联表之间添加数据更改数据需要注意。还是以Phone为例子：
	
	<java>
		Phone.class
		....
		private List<App> apps = new ArrayList<>;
		....
		
		
		App.class
		...
		private Phone phone;
		...
	</java>	
	
以上代码表示Phone和App是一对多的关系，在app的数据库表中会出现自动出现一个`phone_id`字段，表示该app对应的手机。

当需要给一个手机新增一个app时，应该这样操作

	<java>
		// 查找id为2的手机
		Phone phone = DataSupport.find(Phone.class, 2);
		// 新增一个短信App
		App message = new App();
		...
		message.setSize(...);
		...
		message.save;
		
		// 这是关键
		// 将message应用与id为2的手机关联起来
		// 数据库中app表中的message的phone_id字段将变成2
		message.setPhone(phone);
	</java>
	
以上就是关联表的数据新增操作。
   