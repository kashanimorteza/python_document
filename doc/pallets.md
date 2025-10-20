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

# [<span style="color:black;">Pallets</span>](../index.md) 

[Python](index.md) |
[Structure](structure.md) | 
[Example](example.md) | 
[Pallets](pallets.md) |
[Telegram](telegram.md)

<div align="left"><img src="diagram/pallets.jpeg"></div>

<a href="#diagram">Diagram</a> - 
<a href="#flask">Flask</a> - 
<a href="#jinja">Jinja</a> -
<a href="#sqlalchemy">Sqlalchemy</a> - 
<a href="#question">Question</a>  
<a href="#note">Note</a>  


<!------------------------------------------------------------------- [ Flask ] --->
<div class="md5"></div>

## Flask

save local variable on .env file , flask read it automatically

#### <span class="red">Resource</span>

General : 
	<a href="https://palletsprojects.com/" target="_blank">Pallets</a> - 
	<a href="https://flask-sqlalchemy.palletsprojects.com/en/2.x/" target="_blank">flask-sqlalchemy</a> - 
	<a href="https://flask-login.readthedocs.io/en/latest/" target="_blank">flask-login</a>

Tutorial : 
	<a href="https://www.youtube.com/channel/UCkuHzng-3im8CtounzRO-GQ" target="_blank">Alireza Ayinmehr</a> - 
	<a href="https://www.youtube.com/channel/UC-QDfvrRIDB6F0bIO4I4HkQ" target="_blank">Pretty Printed</a>

	


#### <span class="red">Install</span>
	
	pip3 install flask	


#### <span class="red">Run</span>

General

	flask run : only run app.py | wsgi.py	

Windows

	set FLASK_APP=main.py
	flask run
	unset FLASK_APP

	Debug
	-------
	set FLASK_ENV=development
	flask run
	unset FLASK_ENV

Linux	

	Way 1
	-------
	export FLASK_APP=main.py
	flask run
	unset FLASK_APP

	Way 2
	-------
	FLASK_APP=main.py flask run

	Debug
	-------
	export FLASK_ENV=development
	flask run
	unset FLASK_ENV


#### <span class="red">View</span>

<span class="blue">Variable</span>

	@app.route('/a')
	def a():
		return ('<h1>Hello world</h1>') 


	@app.route('/b/<string:data>')        
	def b(data):
		return (f'<h1>{data}</h1>')           


	@app.route('/c/<path:data>')
	def c(data):
		return (f'<h1>{data}</h1>')   

<span class="blue">Blueprint</span>

	app.py
	-----------------
    from flask import Flask
	from admin import admin_bp

    app = Flask(__name__)

    app.register_blueprint(admin_bp)

    app.run("0.0.0.0", "80", debug=True)


	admin.py
	-----------------
    from flask import Blueprint
	from . import views

    admin_bp = Blueprint('admin', __name__, url_prefix='/admin/')

	from .views import index


	views.py
	-----------------
	from . import admin_bp

    @admin_bp.route('/')
    def index():
        return 'Admin index' 


#### <span class="red">Session</span>

1



#### <span class="red">Flash</span>

<span class="blue">Simple</span>

	app.py
	--------------------------------
	from flask import Flask, render_template, flash

	app = Flask(__name__)
	app.secret_key = b'_5#y2L"F4Q8z\n\xec]/'


	@app.route('/')
	def test():
		flash('a')
		flash('b')
		flash('c')
		return render_template('test.html')

	app.run("0.0.0.0", "80", debug=True)
		
	templates/test.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				{% with messages = get_flashed_messages() %}
					{% if messages %}                    
						{% for message in messages %}
						<div> {{ message }} </div> 
						{% endfor %}                    
					{% endif %}
				{% endwith %}
			</h1>
		</body>
	</html>


<span class="blue">Category</span>

	app.py
	--------------------------------
	from flask import Flask, render_template, flash

	app = Flask(__name__)
	app.secret_key = b'_5#y2L"F4Q8z\n\xec]/'


	@app.route('/')
	def test():
		flash('a', category='red')
		flash('b', category='blue')
		flash('c', category='green')
		return render_template('test.html')

	app.run("0.0.0.0", "80", debug=True)
		
	templates/test.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				{% with messages = get_flashed_messages(True) %}
					{% if messages %}                    
						{% for message in messages %}
						<div style="color: {{ message[0] }}"> {{ message[1] }} </div> 
						{% endfor %}                    
					{% endif %}
				{% endwith %}
			</h1>
		</body>
	</html>












<div class="md1"></div>

## Jinja

#### Render html file

	test.py
	--------------------------------
	from flask import Flask

	app = Flask(__name__)

	@app.route('/test')
	def test():
		return Flask.render_template('test.html')
	
	app.run("0.0.0.0", "80", debug=True)


	templates/test.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				this is test.html file
			</h1>
		</body>
	</html>

#### Change defult template folder

	test.py
	--------------------------------
	from flask import Flask

	app = Flask(__name__,template_folder='myTemplateFolder')

	@app.route('/test')
	def test():
		return Flask.render_template('test.html')

	app.run("0.0.0.0", "80", debug=True)


	myTemplateFolder/test.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				this is test.html file
			</h1>
		</body>
	</html>


#### Send varible to template

	test.py
	--------------------------------
	from flask import Flask

	app = flask.Flask(__name__)

	@app.route('/test')
	def test():
		myVariable = 'morteza'
		return flask.render_template('test.html',data = myVariable)

	app.run("0.0.0.0", "80", debug=True)
	

	templates/test.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				{{ data }}
			</h1>
		</body>
	</html>

#### Condition

	test.py
	--------------------------------
	from flask import Flask

	app = flask.Flask(__name__)

	@app.route('/test')
	def test():
		myVariable = 'morteza'
		return flask.render_template('test.html',data = myVariable)

	app.run("0.0.0.0", "80", debug=True)


	templates/test.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				{% if data=='morteza' %}
					aaaa
				{% else %}
					bbb 
				{% endif %}
			</h1>
		</body>
	</html>


#### Loop

	test.py
	--------------------------------
	from flask import Flask

	app = flask.Flask(__name__)

	@app.route('/test')
	def test():
		myVariable = ['reza', 'morteza', 'ahmad']
		return flask.render_template('test.html',data = myVariable)

	app.run("0.0.0.0", "80", debug=True)
		

	templates/test.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				{% for d in data %}
				{{ d }}
				{% endfor %}
			</h1>
		</body>
	</html>

#### Block

	app.py
	--------------------------------
	from flask import Flask,render_template

	app = Flask(__name__)

	@app.route('/test')
	def test():
		return render_template('test.html')

	app.run("0.0.0.0", "80", debug=True)
		
	templates/base.html
	--------------------------------
	<html>
		<head></head>
		<body>
			<h1>
				{% block content %}

				{% endblock %}
			</h1>
		</body>
	</html>

	templates/test.html
	--------------------------------
	{% extends 'base.html' %}
		
	{% block content %}
		this is a test page
	{% endblock %}


















<div class="md1"></div>

## Sqlalchemy

#### Install 
	pip install flask-sqlalchemy


<div class="md1"></div>

## flask-login


<div class="md1"></div>

## Flask-Limiter


<div class="md1"></div>

## flask-sqlalchemy



<div class="md1"></div>

## Question