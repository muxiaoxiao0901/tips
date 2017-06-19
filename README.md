# tips
每天积累的小tips~</br>
### 1.零宽断言</br>
用于查找在某些内容(但并不包括这些内容)之前或之后的东西，也就是说它们像\b,^,$那样用于指定一个位置，这个位置应该满足一定的条件(即断言)，因此它们也被称为零宽断言。断言用来声明一个应该为真的事实。正则表达式中只有当断言为真时才会继续进行匹配。</br>
(?=exp)也叫零宽度正预测先行断言，它断言自身出现的位置的后面能匹配表达式exp。比如\b\w+(?=ing\b)，匹配以ing结尾的单词的前面部分(除了ing以外的部分)，如查找I'm singing while you're dancing.时，它会匹配sing和danc。</br>
(?<=exp)也叫零宽度正回顾后发断言，它断言自身出现的位置的前面能匹配表达式exp。比如(?<=\bre)\w+\b会匹配以re开头的单词的后半部分(除了re以外的部分)，例如在查找reading a book时，它匹配ading。</br>
假如你想要给一个很长的数字中每三位间加一个逗号(当然是从右边加起了)，你可以这样查找需要在前面和里面添加逗号的部分：((?=\d)\d{3})+\b，用它对1234567890进行查找时结果是234567890。</br>
### 2.package.json配置</br>
dependencies和devDependencies对应版本号限定说明</br>
指定版本：比如1.2.2，遵循“大版本.次要版本.小版本”的格式规定，安装时只安装指定版本。</br>
波浪号（tilde）+指定版本：比如`~`1.2.2，表示安装1.2.x的最新版本（不低于1.2.2），但是不安装1.3.x，也就是说安装时不改变大版本号和次要版本号。</br>
插入号（caret）+指定版本：比如`ˆ`1.2.2，表示安装1.x.x的最新版本（不低于1.2.2），但是不安装2.x.x，也就是说安装时不改变大版本号。需要注意的是，如果大版本号为0，则插入号的行为与波浪号相同，这是因为此时处于开发阶段，即使是次要版本号变动，也可能带来程序的不兼容。</br>
latest：安装最新版本。</br>
### 3.http-server在package.json中的配置</br>
`"scripts": {
     "start": "http-server -a 0.0.0.0 -p 8000"
 }`
 
 ```-p 端口号 (默认 8080)
-a IP 地址 (默认 0.0.0.0)
-d 显示目录列表 (默认 'True')
-i 显示 autoIndex (默认 'True')
-e or --ext 如果没有提供默认的文件扩展名(默认 'html')
-s or --silent 禁止日志信息输出
--cors 启用 CORS via the Access-Control-Allow-Origin header
-o 在开始服务后打开浏览器
-c 为 cache-control max-age header 设置Cache time(秒) , e.g. -c10 for 10 seconds (defaults to '3600'). 禁用 caching, 则使用 -c-1
-U 或 --utc 使用UTC time 格式化log消息
-P or --proxy Proxies all requests which can't be resolved locally to the given url. e.g.: -P http://someurl.com
-S or --ssl 启用 https
-C or --cert ssl cert 文件路径 (default: cert.pem)
-K or --key Path to ssl key file (default: key.pem)
-r or --robots Provide a /robots.txt (whose content defaults to 'User-agent: *\nDisallow: /')
-h or --help 打印以上列表并退出 ```

### 4.flex布局</br>
设为flex布局后，子元素的float、clear、vertical-align属性将失效。
