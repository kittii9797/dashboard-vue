<template>
  <section class="content">
    <section class="text">
      <h2>
       {{title}}
        <br/>
          <div class="countdown">
                <div class="count-div">
                    <span class="number months">{{months}}</span>
                    <span>Months</span>
                </div>
                <div class="count-div">
                    <span class="number days">{{days}}</span>
                    <span>Days</span>
                </div>
                <div class="count-div">
                    <span class="number hours">{{hours}}</span>
                    <span>Hours</span>
                </div>
                <div class="count-div">
                    <span class="number minutes">{{minutes}}</span>
                    <span>Minutes</span>
                </div>
                <div class="count-div">
                    <span class="number seconds">{{seconds}}</span>
                    <span>Seconds</span>
                </div>
            </div>
      </h2>
      <p>
        {{description}}
      </p>

        <button type="submit" class="btn"><span>{{buttonText}}</span></button>
    </section>

  </section>
</template>

<script>
export default {
	data() {
		return {
			title: 'Welcome To The Website',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vel lobortis ex. Integer quis tortor aliquam, convallis orci eget, ultrices massa. Maecenas vestibulum dui at nibh ornare, vel commodo ipsum vestibulum.',
			buttonText: 'Subscribe Here',
			seconds: '',
			minutes: '',
			hours: '',
			days: '',
			months: ''
		};
	},
	mounted() {
		const newDate = new Date('may 04 23 23:59:59').getTime();
		const countdown = setInterval(() => {
			const date = new Date().getTime();
			const diff = newDate - date;

			const month = Math.floor((diff % (1000 * 60 * 60 * 24 * (365.25 / 12) * 365)) / (1000 * 60 * 60 * 24 * (365.25 / 12)));
			const days = Math.floor((diff % (1000 * 60 * 60 * 24 * (365.25 / 12))) / (1000 * 60 * 60 * 24));
			const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
			const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
			const seconds = Math.floor((diff % (1000 * 60)) / 1000);

			this.seconds = seconds < 10 ? '0' + seconds : seconds;
			this.minutes = minutes < 10 ? '0' + minutes : minutes;
			this.hours = hours < 10 ? '0' + hours : hours;
			this.days = days < 10 ? '0' + days : days;
			this.months = month < 10 ? '0' + month : month;

			if (diff === 0) {
				clearInterval(countdown);
			}
		}, 1000);
	}
};
</script>

<style lang="css" scoped>
.content {
	align-items: center;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	height: calc(100vh - 15rem);
	background: linear-gradient(45deg, #050505, #1f2020, #1c1b22, #28483e, #182946, #482e00);
	background-size: 600% 100%;
	animation: gradient 16s linear infinite;
	animation-direction: alternate;
}
@keyframes gradient {
	0% {
		background-position: 0%;
	}
	100% {
		background-position: 100%;
	}
}
.content section {
	align-items: center;
	display: flex;
	flex-direction: column;
	justify-content: center;
	height: 100%;
	width: 100%;
}

.text {
	padding-left: 99px;
}

.text h2 {
	color: #fff;
	font-size: 3rem;
	font-weight: 400;
	letter-spacing: 0.4px;
	line-height: 3rem;
	text-align: center;
}

.text h2 strong {
	font-size: 5rem;
	font-weight: 700;
	letter-spacing: -3.5px;
	transition: color 1.5s ease;
	text-align: center;
}

.text p {
	color: #fff;
	font-size: 1rem;
	margin-bottom: 20px;
	margin-top: 15px;
	width: 40vw;
	text-align: center;
}
.countdown {
	display: flex;
	justify-content: center;
	gap: 20px;
}

.countdown > .count-div {
	display: flex;
	flex-wrap: nowrap;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	margin-top: 40px;
	box-shadow: 1px 1px 15px rgba(227, 227, 227, 0.25);
	width: 100px;
	height: 100px;
	border-radius: 5px;
}
.number {
	font-weight: 500;
	font-size: 40px;
	color: #caa78c;
}

div span:last-of-type {
	font-size: 12px;
}

button {
	width: 270px;
	height: 80px;
	border: none;
	outline: none;
	background: #2f2f2f;
	color: #fff;
	font-size: 22px;
	border-radius: 40px;
	text-align: center;
	box-shadow: 0 6px 20px -5px rgba(0, 0, 0, 0.4);
	position: relative;
	overflow: hidden;
	cursor: pointer;
}

.check-box {
	width: 80px;
	height: 80px;
	border-radius: 40px;
	box-shadow: 0 0 12px -2px rgba(0, 0, 0, 0.5);
	position: absolute;
	top: 0;
	right: -40px;
	opacity: 0;
}

.check-box svg {
	width: 40px;
	margin: 20px;
}

svg path {
	stroke-width: 3;
	stroke: #fff;
	stroke-dasharray: 34;
	stroke-dashoffset: 34;
	stroke-linecap: round;
}

.active {
	background: #b5957d;
	transition: 1s;
}

.active .check-box {
	right: 0;
	opacity: 1;
	transition: 1s;
}

.active p {
	margin-right: 125px;
	transition: 1s;
}

.active svg path {
	stroke-dashoffset: 0;
	transition: 1s;
	transition-delay: 1s;
}

/*--Button Styles--*/
.btn {
	font-family: 'Varela Round', sans-serif;
	font-size: 16px;
	text-decoration: none;
	width: 60px;
	height: 60px;
	background: #caa78c;
	color: white;
	display: flex;
	justify-content: center;
	align-items: center;
	position: relative;
	border: 0;
	border-radius: 75px;
	cursor: pointer;
	transition: all 500ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}
.btn span {
	color: transparent;
	transition: all 100ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}
.btn:before {
	content: '';
	position: absolute;
	width: 2px;
	height: 12px;
	background: white;
	transform: rotate(45deg);
	top: 28px;
	transition: all 500ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}
.btn:after {
	content: '';
	position: absolute;
	width: 2px;
	height: 12px;
	background: white;
	transform: rotate(-45deg);
	bottom: 28px;
	transition: all 500ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}

/*--Button Hover Styles--*/
.btn:hover {
	width: 225px;
	transition: all 500ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}
.btn:hover span {
	color: white;
	margin-left: -20px;
	transition: all 500ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}
.btn:hover:before,
.btn:hover:after {
	right: 45px;
	transition: all 500ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}

/*--Button Active Styles--*/
.btn:active,
.btn:focus {
	width: 60px;
	height: 60px;
	background: rgb(86, 173, 86);
	outline: none;
	transition: all 500ms cubic-bezier(0.565, -0.07, 0.14, 1.135);
	transition-timing-function: cubic-bezier(0.565, -0.07, 0.14, 1.135);
}

.btn:active span,
.btn:focus span {
	color: transparent;
}

.btn:active:before,
.btn:focus:before {
	transform: rotate(45deg);
	top: 17px;
	height: 20px;
	margin: auto;
	right: -8px;
	left: 0;
}

.btn:active:after,
.btn:focus:after {
	top: 30px;
	height: 12px;
	transform: rotate(-45deg);
	margin: auto;
	right: 0;
	left: -15px;
}

@media screen and (max-width: 600px) {
	.countdown {
		flex-direction: row;
		align-items: center;
		gap: 10px;
		margin: 20px 0px;
	}
	.countdown > .count-div {
		width: 60px;
		height: 70px;
		margin: 0;
		flex-direction: column;
		justify-content: space-between;
		padding: 10px;
	}
	div span:last-of-type {
		font-size: 10px;
		text-transform: uppercase;
	}
	.number {
		font-size: 34px;
	}
	.text p {
		width: 100%;
		font-size: 15px;
		padding: 0px 20px;
	}
	section.content {
		height: 100%;
	}
	.text {
		padding-left: 0px;
	}
	.text h2 {
		color: #fff;
		font-size: 1.8rem;
		margin-top: 25px;
	}
	button.btn {
		margin-bottom: 20px;
	}
}
</style>



