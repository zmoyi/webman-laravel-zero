## 安装

```
composer config repositories.webman-laravel-zero-foundation vcs https://github.com/mouyong/webman-laravel-zero-foundation

composer require mouyong/webman-laravel-zero:dev-master laravel-zero/foundation:dev-main
```

## 配置项目

**在 config/app.php 中增加如下内容**

```php
return [
    ...

    # 以下内容可参考 config/app.php.new.php 文件
    'name' => "Zero", // 单引号，首字母大写。app:rename 匹配使用的
    // 'version' => app('git.version'),
    'version' => '1.0.0',
    'env' => 'development',
    'timezone' => 'PRC',
    'providers' => [
        App\Providers\AppServiceProvider::class,
    ],
];
```

## 更新 composer.json

`composer.json`

```js
    "bin": ["zero"], // 这行要原样保存，app:rename 使用
    "scripts": {
        // 初始化 laravel-zero/illuminate 与相关配置
        "post-autoload-dump": [
            "MouYong\\WebmanLaravelZero\\ComposerScripts::postAutoloadDump"
        ],
        ...
    }
```

## 使用

```
php zero app:install database
composer require illuminate/routing
```

## 效果截图

![image](https://user-images.githubusercontent.com/10336437/196077662-24bea01e-3b5d-4905-bd84-6530f4ce72c5.png)

![image](https://user-images.githubusercontent.com/10336437/196077648-61c84b76-ba0a-4b16-81d7-b211a5265e9c.png)


