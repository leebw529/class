@[TOC](PHP的系统函数)

# PHP的系统函数

## 1. 有关输出的函数

echo print 语言结构

print_r 

打印复杂变量的信息。

如果想捕捉print_r的输出，可以设置第二个参数为true,print_r 不打印结果，而是返回其输出。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172110691.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

var_dump()



## 2. 时间日期函数
### 1) **time()**

返回从unix纪元（格林威治时间1970一月一日）到当前时间的秒数。

10位整数数字。

常用语保存文章的发布时间，商品的发布时间，修改时间，删除时间。登录时间。

时间戳
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172129637.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)


### 2)  **date()**


格式化时间戳。

date(格式化字符串，[,时间戳]);

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172155403.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172210848.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172223921.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

 

### 3) **microtime()**

返回当前的微秒数，及时间戳字符串。

当使用true参数时，返回对应的浮点数。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172245604.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172257103.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

可以用来生成口令。与md5函数配合

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172308144.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

## 3. 数学函数

  ### 1) **max(),min()**
返回最大值或者是最小值。

```php
/* echo max(1,3,4,7,9);//9
echo "<br>";
echo max(array(2,4,6,8));
echo "<br>";
echo max(0,'hello');
echo "<br>";
echo max('hello',0);
echo "<br>";
echo max('42', 3);
echo "<br>";
echo max(-1,'hello'); */

//$val = min(array(2,4,8),array(2,5,1));


//$val = min('string',array(2,5,7),42);
//$val = max('string',array(2,5,7),42);
//var_dump($val);

```
### 2) **abs()**
返回绝对值
```php
$abs = abs(-4.2);//4.2
$abs = abs(5);//5
$abs = abs(-5);//5
```

### 3) **floor()**

  向下取整

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172319230.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

### 4) **ceil()**

   向上取整；

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172331585.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

### 5) **round()**

   四舍五入取整。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172346752.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)
   ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172358805.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

### 6) **rand() 和 mt_rand()**

   生成随机数。mt_rand 的生成的速度，是rand的四倍多。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172411140.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

### 7) **pow() ,sqrt()**

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172424573.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

​    

   sqrt 平方根

​    

   square  root 的简写

   ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509172437935.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2F5b01f,size_16,color_FFFFFF,t_70#pic_center)

### 8) **案例：使用数学函数生成验证码文字**

   由数字和字母组成随机的字符串，长度固定

   16进制（0-9-A-F）;

   指定整数的随机范围（0-15）

   十进制转成十六进制

   字符串拼接（6次循环）

```php
function randomNum($length = 6){
	$str = '';
	$len = $length;
	for($i=0;$i<$len;$i++){
		$num = mt_rand(0,15);
		$hex = dechex($num);
		$str = $str.$hex;
	}
	return $str;
}

$res = randomNum(7);
echo $res;

```