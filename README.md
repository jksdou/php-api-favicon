# php-get-favicon

获取网站的 Favicon 图标并显示在你的网页上。

### 演示

演示地址：

<a href="http://favicon.uiisc.com/get.php?url=uiisc.com" target="_blank">http://favicon.uiisc.com/get.php?url=uiisc.com</a>

<a href="http://favicon.uiisc.com/favicon/uiisc.com.png" target="_blank">http://favicon.uiisc.com/favicon/uiisc.com.png</a>

### 安装使用

- 上传到网站根目录或者 favicon 文件夹中
- cache 文件夹赋 755 权限
- 然后访问 http://you.url/favicon/get.php?url=https://www.baidu.com
- 如果出现获取不了的情况建议删除缓存再试一次
- 注：文中 favicon 为 api 文件夹，具体自行设置

### 伪静态

方便 CDN 缓存

```nginx
# Nginx规则
rewrite ^/favicon/(.*)\.png$ /get.php?url=$1;

# Apache 规则
# .htaccess
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteRule ^favicon/(.*)\.png$ /get.php?url=$1 [L]
</IfModule>
```

调用方法 http://you.url/favicon/www.baidu.com.png

- 注：目标网址不能有 http(s)://

### 感谢

本项目衍生自 <a href="https://github.com/owen0o0/getFavicon" target="_blank">owen0o0/getFavicon</a>
