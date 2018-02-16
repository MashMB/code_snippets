### jQuery code
```
$(window).on('load', function () {
	$("#loader").fadeOut("slow");
});
```

### CSS code
```
#loader {
	z-index: 999999;
	display: block;
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background: url([path_to_file].gif) 50% 50% no-repeat #[background_color];
}
```

### HTML code
```
<html>
<head>
<meta charset="utf-8">
<meta name="Author" content="full name" />
<meta name="description" content="description" />
<meta name="keywords" content="keywords after coma" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<!--[if IE]>
	<script src="html5shiv.js"></script>
<![endif]-->
<link rel="stylesheet" href="[path_to_styles]" type="text/css" />
<title> [title] </title>
</head>

<body>

	<div id="loader"></div>

</body>

</html>
```