# 03-JavaScript

## 函数

* 匿名函数  

  * 一般出现在注册事件的时候

  ```javascript
  document.onclick = function(){
    
  }
  ```

  * 匿名函数不能单独出现

  * ```
    function(){
      alert(1)
    }
    ```

* 有名函数

  * 有名函数可以单独出现

  * ```
    function a(){
      alert(1)
    }

    a()  // 第一种  加()  自执行
    document.onclick = a; // 充当事件函数
    ```

    ​

* 函数定义

  * 不能加括号执行

  ```javascript
  function a(){
    alert(2)
  }
  a() 
  ```

* 函数表达式

  * 可以加括号执行

  ```javascript
  var a = function(){
    alert(2)
  }
  a()

  +function(){}
  -function(){}
  !function(){}
  ~function(){}
  (function(){})()
  ```

  ### 参数

  * 实参  函数在调用的时候穿的
  * 形参  函数在定义的时候
  * 不定参 （arguments）

  ```
  a( 1, 2 )
  ```


  function a(a, b){  //形参
  	// arguments
    var a = 1 , b = 2 ;
  }
  ```

    ## 函数封装

  ```javascript
  function getId(id){
  	return document.getElementById(id)
  }
  ```

  函数默认`return` 没有就是 `undefined`

  函数只要执行了`return`后面的就不会执行



##　作用域

**当定义的时候 `var`  和 `function`  重名的时候  以`function`为准**

* ```javascript
  var x  = 10 ;
  function a(){
     x = 20    // 弹出20
     var x = 20;  // 弹出10
  }
  a();
  alert(x);
  ```

* js 的解析顺序

  *  定义
    * 找 var
    * 找 function
  *  执行 

* 作用域
  * `script` 是最大的作用域，`function`在执行的时候会产生一个新的作用域
  * 每产生一个新的作用域，按照解析顺序解析代码 
  * 作用域链：
    * 当子作用域没有的时候 ，子作用域可以从父作用域拿取/修改  不可逆

```javascript
alert(x);
alert(a);

var x = 10;
alert(x)
function a(){alert(1)};


/*
	1.定义
		var x;
		function a(){alert(1)}
	2.执行
		alert( x )
		alert( a )
		x = 10
		alert(x)
*/

var x = 10;
fn();
function fn(){
  var x = 20;
  alert(x);
}
alert(x)
/*
	1. 定义：
		var x = 20;
		function fn(){
          	var x = 20;
          	alert(x)
		}
	2. 执行：
		x = 10;
		fn();   ====>    1.定义：
							var x;
						 2。执行：
						 	x = 20;
						 	alert(x);
		alert(x);
*/
只有子作用域找父作用域，没有父作用域找子作用域 

var x = 10;
fn();
function fn(){
  x = 20;
  alert(x);
}
alert(x)

/*
	1. 定义：
		var x = 20;
		function fn(){
          	var x = 20;
          	alert(x)
		}
	2. 执行：
		x = 10;
		fn();   ====>    1.定义：
        
						 2。执行：
		x = 20;			 	 
		alert(x);
*/
```

## JS作用域练习

1.   ```javascript
  var x = 10;
  a();
  function a(){
    alert(x);
    var x =20;
  }
  alert(x)

  /*
  	1.定义：
  		var x ;
  		function a(){
   			 alert(x);
    			var x =20;
  		}
  	2.执行：
  		x = 10;
  		a();   =====>    1.定义：
  							var x;
  						 2.执行：
  						 	alert(x); // undefined
  						 	x = 20;
  		alert(x)   //10
  		
  */
  ```

2.   ```javascript
     alert(a);
     var a = 10;
     alert(a);
     function a(){alert(20)};
     alert(a);
     var a = 30;
     alert(a);
     function a(){alert(40)};
     alert(a)
     //当定义的时候 有var 有function function为准
     /*
     	1.定义：
     		function a(){alert(40)};
     	执行：
     		alert( a );  // 函数块
     		a = 10;
     		alert(a) // 10
     		function a(){alert(20)}; //  定义步骤 跳过
     		alert(a) // 10
     		a = 30;
     		alert(a) // 30
     		alert(a)  // 30
     		
     */
     ```

3.   ```javascript
     var a = 10;
     alert(a);
     a();
     function a(){alert(10)};
     /*
     	1.定义
     	  function a(){alert(10)};
     	2.执行
     	  a = 10；
     	  alert(a); // 10
     	  a();  // 报错   数字不能加括号 
     */
     ```

4.   ```javascript
     a();
     var a = function(){alert(1);};
     a();
     function a(){alert(2);};
     a();
     var a = function b(){alert(3);};
     a();
     /*
     	1.定义：
     		function a(){alert(2);};		
     	2.执行：
     		a();  //　函数　　弹出２
     		ａ　＝　function(){alert(1);};
     		a(); // 1
     		function a(){alert(2);}; // 定义
     		a(); // 1
     		a = function b(){alert(3);};
     		a()  // 3
     */
     ```

5.   ```
      var a = 0;
      function fn(){
        	alert(a)
        	var a = 1;
        	alert(a)
      }
      fn();

      // undefined 1
      ```
     ```

6.   ```javascript
     fn();
     alert(a);
     var a = 0;
     alert(a);
     function fn(){a = 1}

     /*
     	1.定义：
     		var a;
     		function fn(){a = 1}
     	2.执行：
     		fn();  ===>  1. 定义：
     					2。执行
     		a = 1;
     		alert(a) ; // 1
     		a = 0;
     		alert(a);  // 0
     */
     ```

7.    ```javascript
     fn()();
     var a = 0;
     function() fn(){
       alert(a);
       var a = 3;
       function c(){
         aelrt(a)
       };
       return c
     }
     /*
     	1.定义
     		var a
     		function() fn(){
                 alert(a);
                 var a = 3;
                 function c(){
                   aelrt(a)
                 };
                 return c
               }
          2.执行：
          	fn()  ==>  1.定义
          					var a;
          					function c(){
                               	alert(a)
          					}
          				2.执行：
          					alert(a) // undefined
          					a = 3;	
          					retun c;
         	fn()()      === >    1.定义：
         						 2.执行
         					alert(a)  // 3
     		

     */
     ```

8.   ```javascript
     var a = 5;
     function fn(){
       var a = 10;
       alert(a);
       function b(){
         a++;
         alert(a)
       };
       return b;
     };
     var c = fn();  
     c(); 
     fn()();
     c();  

     var c = fn();  // 10
     c();  // 11
     fn()(); // 10 11 
     c();  //12 
     /*
     			1。定义
     				var a;
     				function fn(){
     		    		var a = 10;
     		    		alert(a);
     		    		function b(){
     		    			a++;
     		    			alert(a)
     		    		};
     		    		return b;
     		    	};
     		    	var c;
     		    2. 执行 
     		    	a = 5;
     		    	fn()  ===>  1.定义 
     		    					var a;
     		    					function b(){
     					    			a++;
     					    			alert(a)
     					    		};
     		    				2.执行
     		    					a = 10;
     		    					alert(a);  // 10
     		    					return b;
     		    	c = fn();
     		    	c();  =======>   1.定义：
     		    					 2. 执行
     		    					 	a++;
     		    					 	alert(a); // 11

     		    	fn();  ===>  1.定义 
     		    					var a;
     		    					function b(){
     					    			a++;
     					    			alert(a)
     					    		};
     		    				2.执行
     		    					a = 10;
     		    					alert(a);  // 10
     		    					return b;

     		    	fn()();	=====>	1.定义：
     		    					2. 执行
     		    					 	a++;
     		    					 	alert(a); // 11
     		    	C();    =====>  1.定义：
     		    					2. 执行
     		    					 	a++;
     		    					 	alert(a); // 12
     */
     		    					
     ```






 	
