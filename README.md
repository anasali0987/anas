# anas
calculator made by anas ali bca with the help of html css bootstraps jquery .
<!DOCTYPE html> 
<html lang="en"> 

<head> 
	<meta charset="utf-8" />
	<link rel="stylesheet"
		href= 
"https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"> 
	<script src= 
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"> 
	</script> 
	<script src= 
"https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"> 
	</script> 
	<style> 
		.calculator { 
			padding: 4px; 
			margin: 4px; 
			background-color: #3a4655; 
			width: 100%; 
			height: auto; 
			-webkit-box-shadow: 0px 0px 8px 4px rgba(0, 0, 0, 0.75); 
			-moz-box-shadow: 0px 0px 8px 4px rgba(0, 0, 0, 0.75); 
			box-shadow: 0px 0px 8px 4px rgba(0, 0, 0, 0.75); 
		} 
		
		.form-control { 
			border: 0px solid transparent; 
			padding: 0px; 
			border: 0px; 
			border-radius: 0px; 
		} 
		
		input[type="text"]:disabled { 
			background-color: rgb(150, 117, 117); 
			text-align: right; 
			padding: 8px; 
		} 
		
		.design { 
			text-align: center; 
			border-radius: 4px; 
			width: 100%; 
			height: auto; 
			color: white; 
			padding: 4px; 
			margin: 4px; 
			background-color: #2b2342; 
		} 
	</style> 
</head> 

<body style="background-color:#f8f4f5c4;"> 
    <h1 class="HEADING">CALCULATOR MADE BY: PAWAN SINGH</h1>
	<div class="row"> 
		<div class="col-sm-2 col-md-4">  </div> 
		<div class="col-sm-8 col-md-4"> 
			<br> 
			<br> 
			<br> 
			<br> 
			<div class="container calculator"> 
				<div class="form-input"> 
					<input type="text"
						class="form-control input-lg"
						id="expression"
						value="0"
						disabled> 
					<input type="text"
						class="form-control input-xs"
						id="result"
						value="0"
						disabled> 
				</div> 
				<br> 
				<br> 
				<div class="container-fluid"> 
					<div class="row"> 
						<div class="col-sm-3"> 
							<div class="design">1</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design">2</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design">3</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design"
								style="background-color:rgb(138, 211, 106);"> 
							+</div> 
						</div> 
					</div> 
					<div class="row"> 
						<div class="col-sm-3"> 
							<div class="design">4</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design">5</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design">6</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design"
								style="background-color:orange;"> 
							-</div> 
						</div> 
					</div> 
					<div class="row"> 
						<div class="col-sm-3"> 
							<div class="design">7</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design">8</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design">9</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design"
								style="background-color:orange;"> 
							*</div> 
						</div> 
					</div> 
					<div class="row"> 
						<div class="col-sm-3"> 
							<div class="design">0</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design">.</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design not"
								id="backspace"> ? </div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design"
								style="background-color:orange;"> 
							/</div> 
						</div> 
					</div> 
					<div class="row"> 
						<div class="col-sm-3"> 
							<div class="design"
								style="background-color:red;"> 
							(</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design"
								style="background-color:red;"> 
							)</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design not"
								id="allClear"
								style="background-color:red;"> 
							AC</div> 
						</div> 
						<div class="col-sm-3"> 
							<div class="design not"
								id="equals"
								style="background-color:red;"> 
							=</div> 
						</div> 

					</div> 
				</div> 
			</div> 
		</div> 
		<div class="col-sm-2 col-md-4">  </div> 
	</div> 
	<script> 
		$(document).ready(function() { 
			$(".design").click(function() { 
				if (!$(this).hasClass("not")) { 
					if ($("#expression").val() == 0) 
						$("#expression").val($(this).text()); 
					else 
						$("#expression").val($("#expression").val() + $(this).text()); 
				} 
			}); 

			$('#backspace').click(function() { 
				var value = $("#expression").val(); 
				if (!(parseInt(parseFloat(value)) == 0 && value.length == 1)) 
					$("#expression").val(value.slice(0, value.length - 1)); 
				if (value.length == 1) 
					$("#expression").val("0"); 
			}); 
		}); 

		$("#allClear").click(function() { 
			$("#expression").val("0"); 
			$("#result").val("0"); 
		}); 

		$("#equals").click(function() { 
			var result; 
			try { 
				result = (eval(($("#expression").val()))); 
			} catch (e) { 
				if (e instanceof SyntaxError) { 
					alert("Error! Resetting values."); 
					$("#expression").val("0"); 
					$("#result").val("0"); 
				} 
				if (e instanceof TypeError) { 
					alert("Error! Resetting values."); 
					$("#expression").val("0"); 
					$("#result").val("0"); 
				} 
			} 

			$("#result").val(result); 
			$("#expression").val("0"); 
		}); 
	</script> 
</body> 

</html> 
