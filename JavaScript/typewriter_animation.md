### Typewriter animation in JavaScript (typewriter.js)
```
class Typewriter {

	constructor(holder, phrases, read_time) {
		this.holder = holder;
		this.phrases = phrases;
		this.read_time = parseInt(read_time, 10);
		this.loop_number = 0;
		this.sentence = "";
		this.isDeleting = false;
	}

	animate() {
		let index = this.loop_number % this.phrases.length;
		let full_sentence = this.phrases[index];

		if(this.isDeleting) {
			this.sentence = full_sentence.substring(0, this.sentence.length - 1);
		} else {
			this.sentence = full_sentence.substring(0, this.sentence.length + 1);
		}

		this.holder.innerHTML = '<span style="border-right: 0.08em solid #ffffff">' + this.sentence + '</span>';

		let that = this;
		let delta = 200 - Math.random() * 100;

		if(this.isDeleting) {
			delta /= 2;
		}

		if(!this.isDeleting && this.sentence === full_sentence) {
			delta = this.read_time;
			this.isDeleting = true;
		} else if(this.isDeleting && this.sentence === "") {
			this.isDeleting = false;
			this.loop_number++;
			delta = 500;
		}

		setTimeout(function() {
			that.animate();
		}, delta);
	}

}

window.onload = function() {
	let holders = document.getElementsByClassName("typewriter");

	for(let i = 0; i < holders.length; i++) {
		let sentences = holders[i].getAttribute("phrases");
		let read_time = holders[i].getAttribute("read_time");

		if(sentences) {
			new Typewriter(holders[i], JSON.parse(sentences), read_time).animate();
		}
	}
};
```

### Holder in HTML
```
<h1 class="typewriter" phrases='["Test", "Testing"]' read_time="2000"></h2>
<script src="js/typewriter.js"></script>
```