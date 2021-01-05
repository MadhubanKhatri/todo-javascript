# todo-javascript

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">

    <title>TO DO App</title>
  </head>
  <body class="bg-primary">
  	<div class="container">
  		<div class="card px-4" style="width: 18rem;">
  			<div class="card-header my-2">
  				<b><h3>To Do List</h3></b>
  			</div>
  			<input type="text" id="task_field" placeholder="Add a New Task" class="form-control my-4">

  			<!--Add Item to ongoing list-->
  			<span class="text-muted"><small>Ongoing Tasks</small></span>
  			<ul class="list-group list-group-flush" id="menu">

  			</ul>


  			<!--Add Item to completed list-->
  			<span class="text-muted"><small>Completed Tasks</small></span>
  			<ul class="list-group list-group-flush" id="com_menu">

  			</ul>


  			<div class="container my-3">
  				<button class="btn btn-primary" id='add_btn'>Add Task</button>
  			</div>
  		</div>
  	</div>
    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js" integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW" crossorigin="anonymous"></script>

  </body>
</html>

```

## JAVASCRIPT CODE
```javascript
  <script type="text/javascript">
    	var menu, btn, task, com_menu;
    	menu = document.getElementById('menu');
    	com_menu = document.getElementById('com_menu');
    	task = document.getElementById('task_field');
    	btn = document.getElementById('add_btn');
    	btn.addEventListener('click', function(){
    		
    		var task_val = task.value.toUpperCase();
    		if(task_val)
    		{
    			var li, del_btn, check_button;
    			li = document.createElement('li');
    			del_btn = document.createElement('button');
    			check_button = document.createElement('button');

    			li.appendChild(document.createTextNode(task_val));
    			li.setAttribute('class', 'list-group-item');

    			check_button.setAttribute('type', 'checkbox');
    			check_button.style.float = 'right';
    			check_button.setAttribute('class', 'form-check-input mx-3');

    			check_button.onclick = function(){
    				li.parentNode.removeChild(li);

    				var com_li;
    				com_li = document.createElement('li');
    				com_li.appendChild(document.createTextNode(task_val));
    				com_li.setAttribute('class', 'list-group-item');
    				com_menu.appendChild(com_li);
    			}

    			del_btn.appendChild(document.createTextNode('Delete'));
    			del_btn.style.float = 'right';
    			del_btn.setAttribute('class', 'btn btn-danger btn-sm');

    			del_btn.onclick = function(){
    				li.parentNode.removeChild(li);
    			}

    			li.appendChild(del_btn);
    			li.appendChild(check_button);
    			
    			
    			menu.appendChild(li);
    			task.value = "";
    			

    		}
    		else
    		{
    			alert('Write a Task, Please.');
    		}
    		
    	});
    	

    </script>
```
