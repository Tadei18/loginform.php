# loginform.php
///A simple login form///
<?php
    $name=' ';
	$email=' ';
	$subject=' ';
	$comments=' ';
	$gender=' ';
	$result=' ';
	$skills1=' ';
	$skills2=' ';
	$skills3=' ';
	$skills4=' ';
	$country=' ';
	if(isset($_POST['validate'])){
		if(empty($_POST['name'])){
			$name='<span style="color:red;">The name field is empty</span>';
		}else{
			$name='<span style="color:green;">'.htmlspecialchars($_POST['name']).'</span>';
		}
	if(!empty($_POST['email'])){
		$email='<span style="color:green;">'.htmlspecialchars($_POST['email']).'</span>';
	}else{
		 $email='<span style="color:red;">The email field is empty</span>';
	}
	if(!empty($_POST['subject'])){
		$subject='<span style="color:green;">'.htmlspecialchars($_POST['subject']).'</span>';
	}else{
		 $subject='<span style="color:red;">The subject field is empty</span>';
	}
	$comments='<h3>comments</h3>'.htmlspecialchars($_POST['comments']);
	$gender=htmlspecialchars($_POST['gender']);
	$skills1=htmlspecialchars($_POST['skills1']);
	$skills2=htmlspecialchars($_POST['skills2']);
	$skills3=htmlspecialchars($_POST['skills3']);
	$skills4=htmlspecialchars($_POST['skills4']);
	$country=htmlspecialchars($_POST['country']);
	}else{
		$result= 'There was no input <br>';
	}
?>
<HTML>
    <head>
	<title>LOGIN PANEL</title>
	</HEAD>
	    <body>
		   <form method="POST" action="<?php echo $_SERVER['PHP_SELF'];?>">
		   <table>
		   <tr>
		   <td>NAME *</td>
		   <td><input type="text" name="name"><?php echo $name?></td>
		   </tr>
		   <tr>
		   <td>E-mail Address *</td>
		   <td><input type="text" name="email"><?php echo $email?></td>
		   </tr>
		   	<tr>
		   <td>Subject *</td>
		   <td><input type="text" name="subject"><?php echo $subject?></td>
		   </tr>
		   <tr>
		   <td>Your Gender</td>
		   </tr>
		   <tr>
		     <td>MALE: <input type="radio" Value="male" name="gender"><br>FEMALE: <input type="radio" Value="female" name="gender"></td> 
		   </tr>
		   <tr>
      		 <td> 
			 SKILLS:
			 </td>  
			 <td>
			     <input type="checkbox" name="skills1" value="HTML">: HTML<br>
				 <input type="checkbox" name="skills2" value="php">: PHP <br>
				 <input type="checkbox" name="skills3" value="css">: CSS<br>
				 <input type="checkbox" name="skills4" value="Java">:Java<br>
			 </td>
		   </tr>
		   <tr>
		   <tr>
		     <td>country</td>
			 <td>
			     <select name="country">
				     <option select>select a country</option>
					 <option value="south africa">South Africa</option>
					  <option value="kenya">Kenya</option>
					  <option value="uganda">Uganda</option>
					   <option value="ghana">Ghana</option>
					    <option value="mexico">Mexico</option>
						 <option value="tanzania">Tanzania</option>
						  <option value="rwanda">Rwanda</option>
						   <option value="burundi">Burundi</option>
						    <option value="sudan">Sudan</option>
							 <option value="somalia">Somalia</option>
							  <option value="zambia">zambia</option>
							   <option value="tunisia">Tunisia</option>
				 </select>
			 </td>
		   
		   </tr>
		   <td>Comments</td>
		   <td><textarea name="comments"></textarea></td>
		   </tr>
		   <tr>
		   <td><input type="hidden" value="yes" name="validate"></td>
		   <td><input type="SUBMIT" name="login_submit"></td>
		   </tr>
		   </table>
		   <?php echo $comments.'<br>' ;
		     echo $result.'<br>' ;
			 echo $gender.'<br>' ;
			 echo $skills1.'<br>' ;
			 echo $skills2.'<br>' ;
			 echo $skills3.'<br>';
			 echo $skills4.'<br>';
			 echo $country.'<br>';
		   ?>
		   </form>
		</body>
</HTML>
