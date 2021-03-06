---
layout: post
title: PHP面向对象
description: PHP-Object
tag: PHP
---

## 1、面向对象内容 

* 类：定义了一件事物的抽象特点，具有抽象性

* 对象：类的实例

* 多态：相同的函数或方法可作用于多种类型的对象上获得不同的结果

* 重载：方法具有相同的名称，但是参数列表不同，不同的参数的函数或方法之间，互称为重载函数或方法

* 构造函数：不同于JS，PHP中构造函数位于类中，在配合new操作符的同时，将对象成员变量初始化 

  `function __construct($par1,$par2){$this->url = $par1; $this->title = $par2;}`

```php
<?php
  class Site{
  var $url;
  var $title;
  
  function __construct($par1,$par2){
    $this->url = $par1;
    $this->title = $par2;
  }
  function getUrl(){
    echo $this->url .PHP_EOL ;  //这里PHP_EOL表示换行符 在源代码中HTML输出表现为换行 但在web上没有换行的表现
  }
  function getTitle(){
    echo $this->title;
  }
}
$taobao = new Site('www.taobao.com','淘宝');		//这里自动调用了构造函数 传入了url、title两个参数，将对象中变量初始化
$taobao->getTitle();		//淘宝
echo '</br>';
$taobao->getUrl();			//www.taobao.com
?>
```



* 析构函数：在对象结束生命周期后，系统自动调用析构函数，释放内存


`function __destruct(){.....} `

```php
<?php 
	class Site{
		var $url;
		var $title;

		function __construct($par1,$par2){
			$this->url = $par1;
			$this->title = $par2;
		}
		
		function getUrl(){
			echo $this->url . PHP_EOL;
		}
		function getTitle(){
			echo $this->title . PHP_EOL;
		}

		function __destruct(){
			print "销毁" .$this->title;
		}
	}

	$taobao = new Site("www.taobao.com","淘宝");
	$taobao->getTitle();
	$taobao->getTitle();
	$taobao->getTitle();
?>
```

* 继承

使用关键字 `extends`

`class child extends Parent{......}`

* 访问控制

  PHP对属性或方法的访问控制，是通过在前面添加关键字public（共有），protected（受保护）或private（私有）来实现：

  1. public ：共有的，可以在任何地方被访问
  2. protected：受保护的类成员可以被其**自身以及子类和父类**访问
  3. private ： 私有的类成员只能在其定义的类中访问

* 属性的访问控制

  使用var 声明的属性为**public**

  ```
  <?php
  class Site{
    public $public = 'Public';
    var $var1 = 'var';
    protected $protected = 'Protected';
    private $private = 'Private';
    
  }
  ?>
  ```

  ​





















