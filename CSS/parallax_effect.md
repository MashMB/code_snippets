### Styles for parallax effect
```
.parallax {
	/* Add background image and height in html code*/
	background: no-repeat fixed center;
	background-size: cover;
}
```

### Usage in HTML
```
<div class="parallax" style="height: 100%; background-image: url('img/welcome.png');">
</div>
```

### Styles for centered message in parallax container
```
.message {
	width: 100%;
	position: absolute;
	top: calc(calculated_vertical_center);
	text-align: center;
}
```