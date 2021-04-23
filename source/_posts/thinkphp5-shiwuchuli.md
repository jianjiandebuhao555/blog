---
title: ThinkPHP5 事务处理
date: 2021-04-15 11:54:52
tags:
    - php
    - mysql
    - thinkphp
    - 事务
categories:
    - php
    - mysql
cover: /img/cover.jpg
---

> ThinkPHP 5.0 如何使用 MySql 事务

<!--more-->

-------

### 闭包事务处理

```php
public function delete(){
	//由于第二条语句写的有问题,只执行第一条
	Db::table('user')->delete(1038);
	Db::table('user')->deletesssssss(1039);

	//由于第二条写的有问题，两条删除都不执行
	Db::transaction(function(){
		Db::table('user')->delete(1040);                    
		Db::table('user')->deletesssssss(1041);
	});
}
```

-------

### 手动异常事务处理

```php
public function delete(){
	// 启动事务
	Db::startTrans();
	try{
		$res=Db::table('user')->delete(1039);
		if(!$res){
			throw new \Exception('删除失败');
		}else{
			throw new \Exception('删除成功');
		}
		// 提交事务
		Db::commit();
	} catch (\Exception $e) {
			dump($e->getMessage());
		// 回滚事务
		Db::rollback();
		//注意：我们做了回滚处理，所以id为1039的数据还在
	}
}
```

-------