<script lang="ts">
	import quizData from '$lib/questions.json';

	interface Question {
		question: string;
		alternatives: string[];
		answer: string;
	}

	const questions: Question[] = quizData;

	let currQ = 0;
	let rightAns = 0;

	function submitAnswer(event: Event, question: Question) {
		event.preventDefault();
		const answer = (event.target as HTMLInputElement).value;
		if (answer === question.answer) {
			rightAns++;
		}
		if (currQ < questions.length) {
			currQ++;
		}
	}

	function restartQuiz() {
		currQ = 0;
		rightAns = 0;
	}
</script>

<div class="quiz">
	{#if currQ < questions.length}
		<h3>{questions[currQ].question}</h3>
		{#each questions[currQ].alternatives as alternative}
			<label>
				<input
					class="button-24"
					type="button"
					name={`question_${currQ}`}
					value={alternative}
					on:click={(event) => submitAnswer(event, questions[currQ])}
				/>
			</label>
		{/each}
	{:else}
		<div class="score">
			<p>Your Score</p>
			<p>{rightAns} / {questions.length}</p>
			<button class="restartQuiz" on:click={restartQuiz}>Restart</button>
		</div>
	{/if}
</div>

<style>
	.quiz {
		width: auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}

	.quiz h3 {
		margin-bottom: 2rem;
	}

	.quiz label {
		margin-bottom: 1rem;
	}

	.score {
		font-size: 2rem;
	}

	.restartQuiz {
		margin-top: 2rem;
		display: inline-block;
		padding: 0.5rem 1rem;
		font-size: 1rem;
		border: 1px solid #30ff5d;
		border-radius: 6px;
		background-color: #30ff5d;
		cursor: pointer;
	}

	.button-24 {
		background: #ff4742;
		border: 1px solid #ff4742;
		border-radius: 6px;
		box-shadow: rgba(0, 0, 0, 0.1) 1px 2px 4px;
		box-sizing: border-box;
		color: #ffffff;
		cursor: pointer;
		display: inline-block;
		font-family: nunito, roboto, proxima-nova, 'proxima nova', sans-serif;
		font-size: 16px;
		font-weight: 800;
		line-height: 16px;
		min-height: 40px;
		outline: 0;
		padding: 12px 14px;
		text-align: center;
		text-rendering: geometricprecision;
		text-transform: none;
		user-select: none;
		-webkit-user-select: none;
		touch-action: manipulation;
		vertical-align: middle;
	}

	@media (min-width: 768px) {
		.button-24 {
			font-size: 18px;
			line-height: 18px;
			min-height: 48px;
			padding: 14px 16px;
		}
		.quiz h3 {
			margin-bottom: 3rem;
			font-size: 2rem;
		}
		.button-24:hover,
		.button-24:active {
			background-color: initial;
			background-position: 0 0;
			color: #ff4742;
		}
	}

	.button-24:active {
		opacity: 0.5;
	}
</style>
