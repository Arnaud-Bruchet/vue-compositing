<template>
	<div class="courses-container">
		<div class="course">
			<div class="course-preview" :style="{backgroundColor: coursesColor}">
				<h6>Nom du cours</h6>
				<h3>{{ courseTitle }}</h3>
			</div>
			<div class="course-info">
				<h6>Chapter {{ chapterNumber }}</h6>
				<h2>{{ chapterTitle }}</h2>
				<button class="btn" @click="courseSelector">Select</button>
			</div>
		</div>
	</div>
</template>

<script>

export default {
	name: "CciCard",
	props: {
		chapterTitle:{
			type: String
		},
		chapterNumber:{
			type: Number
		},
		coursesColor: {
			type: String,
			default: '#000000',
		},
		courseTitle: {
			type: String,
			default: "Javascript basic"
		},
		cardId: {
			type: Number,
		},
	},
	components: {},
	data: () => ({
	}),
	methods: {
		courseSelector() {
			console.log('👶 cours sélectionné ', this.cardId)

			// On déclenche un événement custom
			// Son nom est arbitraire et ne correspond pas aux événements classiques
			this.$emit('onCourseSelected',{cardId: this.cardId})
		}
	},
};
</script>

<style scoped>
.courses-container {
	font-family: "Muli", sans-serif;
	display: flex;
	align-items: center;
	justify-content: center;
	color: black;
	flex-direction: column;
}

.course {
	background-color: #fff;
	border-radius: 10px;
	box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
	display: flex;
	max-width: 100%;
	margin: 20px;
	overflow: hidden;
	width: 700px;
}

.course h6 {
	opacity: 0.6;
	margin: 0;
	letter-spacing: 1px;
	text-transform: uppercase;
}

.course h2 {
	letter-spacing: 1px;
	margin: 10px 0;
}

.course-preview {
	color: #fff;
	padding: 30px;
	background-color: #2a265f;
	max-width: 250px;
}

.course-preview a {
	color: #fff;
	display: inline-block;
	font-size: 12px;
	opacity: 0.6;
	margin-top: 30px;
	text-decoration: none;
}

.course-info {
	padding: 30px;
	position: relative;
	width: 100%;
}

.btn {
	background-color: #2a265f;
	border: 0;
	border-radius: 10px;
	box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
	color: #fff;
	font-size: 16px;
	padding: 12px 25px;
	position: absolute;
	bottom: 30px;
	right: 30px;
	letter-spacing: 1px;
}
</style>
