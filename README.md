# aTpl     
a smart  library of javascript template. it support syntax like for and if etc. you can use it in ie5+, chrome, firefox, opera, safair and mobile explorer.        
    
# Install     
   
+ in your html, you just do like this        
```    
<script src="aTpl.min.js"></script>         
```    
+ or you use requireJs          
```    
define(["aTpl"], function () {       
	// your code       
});       
```      
+ or maybe you use seaJs      
```        
seaJs.use('aTpl');       
``` 

# Example      
```   
<script src="../src/aTpl.js"></script>           
<div id="demo"></div>           
<script id="test" type="text/aTpl">           
	<div>负责人：{{ aTpl.name }}</div>           
	<div>性别：{{ aTpl.sex===1 ? '男': '女' }}</div>           
	<div>表达式：{{ 12/4 }}</div>           
	<ul>           
	{{@ for(var i = 0, _l = aTpl.contact.length; i < _l; i++){ }}           
		{{@ if(aTpl.contact[i].name === '张三') { }}           
	    	<li>           
		        <span>姓名：{{ aTpl.contact[i].name + '条件输出' }}</span>           
		        <span>性别：{{ aTpl.contact[i].sex===1 ? '男': '女' }}</span>           
	    	</li>           
	    {{@ } else { }}           
		    <li>           
		        <span>姓名：{{ aTpl.contact[i].name }}</span>           
		        <span>城市：{{ aTpl.contact[i].sex===1 ? '男': '女' }}</span>           
	    	</li>           
	    {{@ } }}           
	{{@ } }}           
	</ul>           
</script>           
<script>           
	var data = {           
	    name: '测试',           
	    sex: 1,           
	    contact: [{name: '张三', sex: 1},           
	    	{name: '李四', sex: 2}]           
	};           
	var temp = document.getElementById('test');           
	aTpl.template(temp).render(data, function(html){           
	    document.getElementById('demo').innerHTML = html;           
	});           
</script>           
```    


# Method  
  
## config    
set the open and end flag, example: aTpl.config({start: '{{', end: '}}'})   
       
## template   
set template, your type must set 'text/aTpl'    
      
## render   
render the data to the template    
    
# Attention   
you can also use it with jQuery.    
       
       
# Release       
version: 1.0.0     
 + support for and if syntax.      
 + support config the start and end flag.     
