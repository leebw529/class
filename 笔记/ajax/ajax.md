| 错误码  | 错误详情       |
| ---- | ---------- |
| 1001 | 用户名不能为空    |
| 1002 | 邮箱不能为空     |
| 1003 | 密码不能为空     |
| 2001 | 用户名长度限制    |
| 2002 | 用户名不能有特殊字符 |
| 2003 | 用户名不能以数字开头 |
| 3001 | 用户名已存在     |



## 原生Ajax请求：

### get请求：

```javascript
var ajax = null;
//创建ajax对象
if(window.XMLHttpRequest){
	ajax= new XMLHttpRequest();
}else{
	ajax = new ActiveXObject('Microsoft.XMLHTTP'); //兼容IE
}
//获取表单的数据
var str =  'user_name='+document.querySelector('input[name=user_name]').value+'&email='+document.querySelector('input[name=email]').value+'&pass='+document.querySelector('input[name=pass]').value;
//2. 建立连接
ajax.open('get','getData.php?'+str);
//3. 发送请求
ajax.send();
//4. 监听状态
ajax.onreadystatechange = function(){
	//正确返回的时候
	if(ajax.readyState==4 && ajax.status==200){
		var re = JSON.parse(ajax.responseText);
		if(re.code!=200){
			document.getElementById('error').innerText = re.message;
		}else{
			if(confirm('注册成功,点击跳转首页')){
				location.href  = '01index.html';
			}else{
				location.href = 'login.html';
			}
		}
	}
}
```

### post请求

```javascript
//1. 创建对象
//兼容IE
var ajax = null;
if(window.XMLHttpRequest){
	ajax= new XMLHttpRequest();
}else{
	ajax = new ActiveXObject('Microsoft.XMLHTTP');
}
//获取表单的数据
var str =  'user_name='+document.querySelector('input[name=user_name]').value+'&email='+document.querySelector('input[name=email]').value+'&pass='+document.querySelector('input[name=pass]').value;
//2. 建立连接
ajax.open('post','postData.php');
//3. 发送请求
ajax.setRequestHeader('Content-type','application/x-www-form-urlencoded');
ajax.send(str);
//4. 监听状态
ajax.onreadystatechange = function(){
	//正确返回的时候
	if(ajax.readyState==4 && ajax.status==200){
		var re = JSON.parse(ajax.responseText);
		if(re.code!=200){
			document.getElementById('error').innerText = re.message;
		}else{
			if(confirm('注册成功,点击跳转首页')){
				location.href  = 'index.html';
			}else{
				location.href = 'login.html';
			}
		}
	}
}
```

### 区别

> + get数据在建立连接的时候放在url后面，post数据是放在send方法里面
>
>
> + post请求在发送的时候由于数据需要进过http头部进行传递，需要对数据进行编码，所以要告诉后端头部信息的编码方式。
>
>   ajax.setRequestHeader('Content-type','application/x-www-form-urlencoded');
>
> + PHP后端在接受的时候使用超全局数组不同

## 案例

**随机点名产生器**

前端点击一个按钮，点击按钮请求后端，后端产生随机点名的名字，返回给前端，前端展示出来。





### 作业

点菜器：

前端显示菜单列表 

每一道菜都可以点击，点击之后前端显示变为灰色，不能再次点击 ，后端在文件中记录点过这个道菜了

