<template>
<div class="text-center fixed-bottom">
    <div class="slider">

		<figure>
	
			<div class="slide" v-for="item in data" v-bind:key="item">
				<div class="text-slide">
					<span class="caption-one">{{item.title}}</span>
					<span class="caption-two">{{item.description}}</span>
				</div> 
				<div class="fade-slide"></div>
				<img :src="item.img" />
			</div>

		</figure>

	</div>
</div>
</template>

<script>
export default {
	data() {
		return {
			data: [
				{
					title: 'Alexey Topolyanskiy',
					description:
						'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua',
					img: 'https://fastly.picsum.photos/id/1015/5000/3333.jpg?hmac=YiHIqvsVlhZoViBg5mG13IvI50oqAmgy79NY-PP_DEw'
				},
				{
					title: 'Philippe Wuyts',
					description:
						'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua',
					img: 'https://fastly.picsum.photos/id/1016/3844/2563.jpg?hmac=WEryKFRvTdeae2aUrY-DHscSmZuyYI9jd_-p94stBvc'
				},
				{
					title: 'Andrew Ridley',
					description:
						'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua',
					img: 'https://fastly.picsum.photos/id/1018/3914/2935.jpg?hmac=3N43cQcvTE8NItexePvXvYBrAoGbRssNMpuvuWlwMKg'
				}
			]
		};
	}
};
</script>

<style scoped>
.slider {
	position: relative;
	max-height: 300px;
	overflow: hidden;
}

.slide img {
	max-width: 100%;
	object-fit: cover;
	object-position: center;
	height: 100%;
	width: 100%;
	position: relative;
	bottom: 100px;
}

.slide {
	display: block;
	-webkit-animation: fadein 2s; /* Safari, Chrome and Opera > 12.1 */
	-moz-animation: fadein 2s; /* Firefox < 16 */
	-ms-animation: fadein 2s; /* Internet Explorer */
	-o-animation: fadein 2s; /* Opera < 12.1 */
	animation: fadein 2s;
}

.text-slide {
	position: relative;
	display: flex;
	flex-direction: column;
	top: 20%;
	left: 10%;
}

.slide .caption-one {
	color: #fff;
	font-size: 25px;
	font-weight: bold;
	z-index: 10;
}

.slide .caption-two {
	color: #fff;
	margin-top: 15px;
	font-size: 16px;
	font-weight: normal;
	z-index: 10;
	width: 450px;
}

@keyframes slidy {
	0% {
		left: 0%;
	}
	20% {
		left: 0%;
	}
	40% {
		left: -100%;
	}
	60% {
		left: -100%;
	}
	80% {
		left: -200%;
	}
	100% {
		left: -200%;
	}
}

.slider {
	overflow: hidden;
}
.slider figure {
	position: relative;
	width: 300%;
	margin: 0;
	left: 0;
	text-align: left;
	font-size: 0;
	animation: 10s slidy infinite;
	display: flex;
	height: 175px;
}
.slide {
	width: 33.33%;
}

.fade-slide {
	position: absolute;
	width: 100%;
	height: 100%;
	z-index: 1;
	bottom: 0;
	background-image: linear-gradient(to right, #000000ad, #ffffff00, #ffffff00, #ffffff00);
}

/* mobile */
@media only screen and (max-width: 600px) {
	span.caption-two {
		width: 275px !important;
	}
	.slider {
		position: relative;
		max-height: 360px;
		overflow: hidden;
	}
	.text-slide {
		top: 20%;
	}
	.slide .caption-one {
		font-size: 23px;
	}
	.slide .caption-two {
		font-size: 14px;
	}
	.slider figure {
		height: 190px;
	}
	.slide img {
		bottom: 115px;
	}
}
</style>