funchat1.html
=============
<!DOCTYPE html>
<html>
	<head>
		<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
		<script type="text/javascript" src="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js"></script>
		<script type="text/javascript" src="http://cdn.firebase.com/v0/firebase.js"></script>
		<script type="text/javascript" src="https://cdn.firebase.com/js/simple-login/1.4.1/firebase-simple-login.js"></script>
		<link rel="stylesheet" href="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css">
		<link href="http://netdna.bootstrapcdn.com/font-awesome/4.1.0/css/font-awesome.css" rel="stylesheet">
		<style>
			.form-control {
				background-color: #F4FA58;
				color: #A4A4A4; 
				
			}
			.modal-title{
				color: #40FF00;
			}
			.form-control input:focus{
				border: 3px solid #40FF00;
				background: #ffffff;
			}
			#log{
				background-color: #FE9A2E;
			}
			.bird{
				color: #9FF781;
	
			}	
			
		
		</style>
		<script type="text/javascript">
		var firebase = new Firebase("https://funchat.firebaseio.com");
		var firebaseLogin = new FirebaseSimpleLogin(firebase, onLogin);
		
		// setup function
		function setup() {
			$('#loginButton').click(onLoginClicked);
			
		}
		function onLoginClicked () {
			var e =$('#loginEmail').val();
			var p = $('#loginPassword').val();
			firebaseLogin.login('password',{email: e, password: p});
		}

	
		
		function onLogin(error, user) {
			if (error) {
				// Handle the login error.
			}
			else if (user) {
				// Handle the successfully logged in user.
				$('.modal').modal('hide');
				alert(user.provider + " - " + user.id);
			}
			else {
				$('.modal').modal('show');

				//var e=prompt("What's your email?");
				//var p=prompt("What's your password?");
				//firebaseLogin.login('password', {"email": e, "password": p});
			}
		}
		
		// Run the setup function when the document is loaded.
		$(document).ready(setup);
		</script>
	</head>
	

	</div>
	<body>
	<div class="container">
		<div class='row'>
			<div class="col-md-3">
				<h1>Aditya Bhardwaj</h1>
				<h5 class="bird">Beat Kalen's flappy bird score</h5>
				<a href="http://flappybird.io/" class= "bird">Click Here</a>
			</div> 
			<div class="col-md-9" id="notificationList">
				<div class="not">
					<h3>Aditya Singh shared a picture <i class="fa fa-paw"></i></h3>	
					<img src = "http://media.npr.org/assets/artslife/arts/2009/11/agassi-86f9bd5c6a13da80a9367df8f9b32faecb953441-s6-c30.jpg">
				</div>
			</div>
		</div>
	</div>
		<div class="modal fade">
	  <div class="modal-dialog">
	    <div class="modal-content">
	      <div class="modal-header">
	        <button type="button" class="close" data-dismiss="modal" aria-hidden="true">&times;</button>
	        <h4 class="modal-title">Login</h4>
	      </div>
	      <div class="modal-body">
	        <input type="email" class="form-control" placeholder="email address" id="loginEmail">
	        <input type="password" class="form-control" placeholder="password" id="loginPassword">
	      </div>
	      <div class="modal-footer">
	        <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
	        <button type="button" class="btn btn-default" data-dismiss="modal" id ="log">Login</button>
	      </div>
	    </div><!-- /.modal-content -->
	  </div><!-- /.modal-dialog -->
		</div><!-- /.modal -->
	
		
	</body>
</html>
