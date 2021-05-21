<html>
<head>

<meta charset="utf-8"/>
<title>注册表单</title>
<link href="注册表单样式.css" rel="stylesheet"/>
</head>

<body>
<h1 class="title1">华东理工大学社团 </h1>
<div class="container">

<form name=myForm method="post" >

<fieldset>
 <legend>用户注册</legend>
    <label for="txtnumber">请输入学号</label>
       <input class="textrad" type="text" name="myname" onblur="validatenumber(this.value)"><br/>
    <label for="txtname">请输入姓名</label>
       <input class="textrad" type="text" name="myname" id="txtname" ><br/>
    <label for="txtpassword">请输入密码</label>
       <input class="textrad" type="password" id="mytxtpas1" onblur="checkZmOrNum(this.value)" placeholder="密码格式须为字母或数字"/><br/>
	 <label for="txtpassword">请确认密码</label>
       <input class="textrad" type="password" id="mytxtpas2" onblur="rcheckZmOrNum(this.value)" placeholder="请确认您的密码" /><br/>   
    <label for="txtemail">请输入邮箱</label>
       <input class="textrad" type="text" name="myemail" id="email" onblur="test(this.value)" ><br/>
    <label for="txttel">请输入电话</label>
       <input class="textrad" type="text" onblur="validatemobile(this.value)"><br/>
	<label for="txtxueyuan">您的学院是</label>
 <select class="xueyuan" size="1" name="xueyuan" id=xueyuan >
   <option value="x1"> 化工学院</option>
   <option value="x2"> 化学与分子工程学院</option>
   <option value="x3"> 生物工程学院</option>
   <option value="x4">药学院</option>
   <option value="x5">材料科学与工程学院</option>
   <option value="x6"> 信息科学与工程学院</option>
   <option value="x7"> 机械与动力工程学院</option>
   <option value="x8"> 资源与环境工程学院</option>
   <option value="x9"> 商学院</option>
   <option value="x10"> 社会与公共管理学院</option>
   <option value="x11">  理学院</option>
   <option value="x12">  艺术设计与传媒学院</option>
   <option value="x13">  外国语学院</option>
   <option value="x14">  法学院</option>
   <option value="x15"> 体育科学与工程学院</option>
   <option value="x16"> 马克思主义学院</option>
   <option value="x17">  中德工学院</option>
   <option value="x18">  国际卓越工程师学院</option>
 </select></br>
 <label for="lblsex">您的性别是</label>
	   <span>男</span><input type="radio"name="sex" value="男" id="man">
       <span>女</span><input type="radio"name="sex" value="女" id="woman">
	<label for="inputdata"> 您的生日是</label>
       <input class="textrad" type="date" name="mydata" id="inputdata" >
	<label for="mymessage">您的简介</label>
	   <textarea name="mymessage" id="mymessage" rows="5" cols="45">
	   </textarea>
</fieldset>	   
 <input  class="butra" type="submit" name="Submit" value="注册" onclick="check()">
 <input class="butra" type="reset" name="取消" id="reset" value="取消">


</form>
</div>

<script type="text/javascript"> 
//验证学号
function validatenumber(number)
{ 
   
	if(number.length>8)
	{alert("请输入正确的学号");
	return false;
	}
	
}
//验证密码
function checkZmOrNum(zmnum){
 var zmnumReg=/^[0-9a-zA-Z]*$/; 
 
      if(zmnum!=""&&!zmnumReg.test(zmnum)){   
        alert("只能输入是字母或者数字,请重新输入");   
        zmnum="";
         return false;  
         }
	}
//验证密码是否一致
function rcheckZmOrNum(zmnum)
{

  if(mytxtpas1.value!=mytxtpas2.value)
  {alert("两次输入密码不一致")
   mytxtpas1.value ="";
   mytxtpas2.value ="";
   return false;
  }

}
//验证邮箱
 function test(obj)
 {
       var myreg = /^([a-zA-Z0-9]+[_|\_|\.]?)*[a-zA-Z0-9]+@([a-zA-Z0-9]+[_|\_|\.]?)*[a-zA-Z0-9]+\.[a-zA-Z]{2,3}$/;
      if(!myreg.test(obj))
     {
           alert('请输入有效的邮箱！');
          myreg.focus();
          return false;
      }
}
//验证手机号
function validatemobile(mobile) 
       { 
          if(mobile.length!=11) 
          { 
              alert('请输入有效的手机号码，需是11位！');
              return false; 
          } 
           
          var myreg = /^(((13[0-9]{1})|(15[0-9]{1})|(18[0-9]{1}))+\d{8})$/; 
          if(!myreg.test(mobile)) 
          { 
              alert('请输入有效的手机号码！'); 
              return false; 
          } 
      } 
//验证输入项不为0
function check()
{
   for(var i=0;i<document.myForm.elements.length-1;i++)
   {
     if(document.myForm.elements[i].value=="")
	 {
	   alert("请检查输入项是否完整");
	   document.myForm.elements[i].focus();
	   return false;
	 }
   }
   return true;
}
	
</script> 


</body>
</html>
