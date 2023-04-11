<script lang="ts">
	import { onMount } from 'svelte';
	import quizData from '$lib/questions.json';

	type Answer = string | null;

	interface Question {
		question: string;
		alternatives: string[];
		answer: Answer;
	}

	const questions: Question[] = quizData;

	let currentQuestion = 0;
	let correctAnswers = 0;

	function submitAnswer(event: Event, question: Question) {
		event.preventDefault();
		const answer = (event.target as HTMLInputElement).value;
		if (answer === question.answer) {
			correctAnswers++;
		}
		if (currentQuestion < questions.length - 1) {
			currentQuestion++;
		}
	}

	onMount(() => {
		questions.forEach((question) => {
			if (!question.hasOwnProperty('answer')) {
				question.answer = null;
			}
		});
	});
</script>

{#if currentQuestion <= questions.length}
	<div class="quiz">
		<h3>{questions[currentQuestion].question}</h3>
		<ul>
			{#each questions[currentQuestion].alternatives as alternative}
				<li>
					<label>
						<input
							type="radio"
							name={`question_${currentQuestion}`}
							value={alternative}
							on:change={(event) => submitAnswer(event, questions[currentQuestion])}
						/>
						{alternative}
					</label>
				</li>
			{/each}
		</ul>
	</div>
{:else}
	<div class="score">
		<h2>Your Score</h2>
		<p>{correctAnswers} / {questions.length}</p>
	</div>
{/if}
