<style>
.md0{padding-bottom: 150px;}
.md1{padding-bottom: 75px;}
.md2{padding-bottom: 50px;}
.md3{padding-bottom: 25px;}
.md4{padding-bottom: 5px;}
.md5{padding-bottom: 10px;}
.a{display: inline-block;width: 50px;background-color: white}
.b{display: inline-block;width: 150px;background-color: white}
.c{display: inline-block;width: 450px;background-color: white}
.d{display: inline-block;width: 400px;background-color: white}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
.red{color:#E74C3C}
.blue{color:#3498DB}
.green{color:#28B463}
table{border: 0px solid black;}
.child {display:inline-block;vertical-align: top;margin-right: 10px;}
</style>

# [<span style="color:black;">Python</span>](../index.md) 

[Python](index.md) |
[Structure](structure.md) | 
[Example](example.md) | 
[Pallets](pallets.md) |
[Telegram](telegram.md)

<div align="left"><img src="diagram/python.jpeg"></div>

<a href="#resource">Resource</a> - 
<a href="#install">Install</a> - 
<a href="#interpretation">Interpretation</a> - 
<a href="#package-manager">Package manager</a> - 
<a href="#virtual-environments">Virtual environments</a> - 
<a href="#question">Question</a> - 
<a href="#note">Note</a>  



<!------------------------------------------------------------------- [ Resource ] --->
<div class="md5"></div>

## Resource

#### General
<a href="https://www.python.org/" target="_blank">Python</a> - 
<a href="https://pypi.org/" target="_blank">pypi</a> - 
<a href="https://jupyter.org/" target="_blank">jupyter</a> - 

#### Learn
<a href="https://docs.python.org/3/" target="_blank">Python Doc</a> - 
<a href="https://www.py4e.com/lessons" target="_blank">py4e</a> - 
<a href="https://www.learnpython.org/" target="_blank">learnpython</a> - 
<a href="https://www.tutorialspoint.com/python/index.htm" target="_blank">tutorialspoint</a> - 
<a href="https://www.w3schools.com/python/" target="_blank">w3schools</a> - 
<a href="https://www.quackit.com/python/tutorial/" target="_blank">quackit</a> - 
<a href="https://toplearn.com/courses/2150/%D8%A2%D9%85%D9%88%D8%B2%D8%B4-%D8%B1%D8%A7%DB%8C%DA%AF%D8%A7%D9%86-%D9%BE%D8%A7%DB%8C%D8%AA%D9%88%D9%86-(-python-)" target="_blank">toplearn</a>

#### Tools
<a href="https://jsonplaceholder.typicode.com/" target="_blank">jsonplaceholder</a>



<!------------------------------------------------------------------- [ Install ] --->
<div class="md1"></div>

## Install

    sudo apt autoremove python3.8
	sudo apt install python3.9
	sudo apt install python3-pip	    
	sudo apt install python3.9-venv
    sudo apt install ipython3
	sudo python3.9 -m pip install --upgrade pip
  
#### VsCode
	
	Install extension : python, pylint



<!------------------------------------------------------------------- [ Interpretation ] --->
<div class="md1"></div>

## Interpretation

	python3.9 --version



<!------------------------------------------------------------------- [ Package manager ] --->
<div class="md1"></div>

## Package manager

	pip --version

	pip install pylint    
	pip install python-dotenv
	pip install jupyterlab
	pip install pysqlite3
	pip install psycopg2-binary
	pip install mysql-connector-python



<!------------------------------------------------------------------- [ Virtual environments ] --->
<div class="md1"></div>

## Virtual environments

	python3.9 -m venv .myENV 
	source .myENV/bin/activate
	deactivate



<!------------------------------------------------------------------- [ Question ] --->
<div class="md1"></div>

## Question

1 - فانکشنی هست که object بصورت ورودی میگیرد این یعنی چی؟

	class range(object):

2 - وب سوکت چگونه بدون تاخییر گوش میکند و میفهمد هنگامی که کانکشن از کلاینت می آید آن تیکه از کد را اجرا کند ؟



<!------------------------------------------------------------------- [ Note ] --->
<div class="md1"></div>

## Note

	on any folder if exist __init__.py you can import from that file like this: from . import myVariable

	for import fromo same folder we can use of '.', like this : from .lib import myclass	

	save local variable on .env file , flask read it automatically
