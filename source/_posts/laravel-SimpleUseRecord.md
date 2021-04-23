---
title: Laravel 简单使用记录
date: 2021-04-15 11:48:08
tags:
    - Laravel
    - 使用记录
categories:
    - php
    - laravel
cover: /img/cover.jpg
---

> 本文对应的 `Laravel` 版本为 `7.x`
> 中文在线文档地址：[https://learnku.com/docs/laravel/7.x](https://learnku.com/docs/laravel/7.x)

<!--more-->

-------

### 快速创建模型、控制器、迁移文件

```shell
# 创建 `API` 控制器及关联模型和对应迁移文件
# `DemoController`控制器可自行定义目录路径
# 如：`Api/DemoController` 生成将在 `app/Http/Controllers/Api/` 目录下
php artisan make:model Demo -m && php artisan make:controller DemoController --api --model=Demo

# 创建后台控制器及关联模型和对应迁移文件
# `DemoController`控制器可自行定义目录路径
# 如：`Admin/DemoController` 生成将在 `app/Http/Controllers/Admin/` 目录下
php artisan make:model Demo -m && php artisan make:controller DemoController --resource --model=Demo

# `Demo` 为对应数据表名
```
-------

### 迁移文件

###### 请参照 [文档(数据库迁移)](https://learnku.com/docs/laravel/7.x/migrations/7496) 进行完善后运行以下命令

###### 给表添加注释

```php
use Illuminate\Support\Facades\DB;

public function up()
{
    Schema::create('table', function (Blueprint $table) {
        $table->id();
        $table->string("test")->comment("字段注释说明");
        $table->softDeletes();
        $table->timestamps();
    });
    # 添加表注释，注意此处的 `table` 必须是带上前缀的表全名
    DB::statement("ALTER TABLE `table` comment '表注释说明'");
}
```

### 运行迁移创建数据表

```shell
php artisan migrate
```

-------

### 路由设置

##### 资源路由

```php
# `Name` 访问 `uri`；`Controller` 访问控制器
Route::resource("Name", "Controller");
```

| 请求方式 | URI | 访问 | 路由名称 |
|:-------:|:-------:|:-------:|:-------:|
| GET | /demo | index | demo.index |
| GET | /demo/create | create | demo.create |
| POST | /demo | store | demo.store |
| GET | /demo/{id} | show | demo.show |
| GET | /demo/{id}/edit | edit | demo.edit |
| PUT/PATCH | /demo/{id} | update | demo.update |
| DELETE | /demo/{id} | destroy | demo.destroy |

##### API 资源路由

```php
# `Name` 访问 `uri`；`Controller` 访问控制器
Route::apiResource("Name", "Controller");
```

| 请求方式 | URI | 访问 | 路由名称 |
|:-------:|:-------:|:-------:|:-------:|
| GET | /demo | index | demo.index |
| POST | /demo | store | demo.store |
| GET | /demo/{id} | show | demo.show |
| PUT/PATCH | /demo/{id} | update | demo.update |
| DELETE | /demo/{id} | destroy | demo.destroy |

-------