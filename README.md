# Learn_Nginx



## 安装或者卸载 (恢复默认配置的方法)

```

   67  sudo apt-get --purge remove nginx
   68  sudo apt-get --purge remove nginx-common
   69  sudo apt-get update
   70  sudo apt-get install nginx

```

 

### Nginx 设置代理或者反向代理的位置

```bash
/etc/nginx/sites-available/
这个文件夹
default
这个文件夹下面的 default文件，用github仓库中的server替换就行

```

![image-20241116221737718](https://ckqqqq-qiker-image-service.oss-cn-beijing.aliyuncs.com/typora-image/image-20241116221737718.png)



### 注意不要添加多个server配置，就在default中改就行，访问ip看到的welcome界面就是default中的

```
"/etc/nginx/nginx.conf" 这个文件夹下面import 了default的所有文件
	include /etc/nginx/conf.d/*.conf;
	include /etc/nginx/sites-enabled/*;
如果在default 和 nginx.conf 中同时加了server会有冲突
如果只在nginx.conf中加server会有bug
最好是在sites-enabled中加网站转发文件
```

