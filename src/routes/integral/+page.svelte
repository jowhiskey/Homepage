<script lang="ts">
	import { BookOpen } from '@lucide/svelte';
</script>

<div class="integral-page">
	<div class="integral-content">
		<div class="icon-wrapper">
			<BookOpen size={48} />
		</div>
		<h1>Integral</h1>
		<p class="subtitle">
			Math notation is confusing. Integral makes it easy by letting you just type as your heart desires!
		</p>

		<div class="placeholder">
			<p class="coming-soon">Documentation coming soon...</p>
			<p class="temp-message">
				We're working hard to create detailed documentation, tutorials, and examples. Stay tuned!
			</p>
		</div>

		<a href="/" class="back-link">← Back to Home</a>
	</div>
</div>

<style>
	.integral-page {
		min-height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 2rem;
		background: linear-gradient(to bottom, #0f172a, #1e293b);
		padding-top: 8rem;
	}

	.integral-content {
		text-align: center;
		max-width: 600px;
		width: 100%;
	}

	.icon-wrapper {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		width: 96px;
		height: 96px;
		background: rgba(167, 139, 250, 0.1);
		border: 2px solid rgba(167, 139, 250, 0.3);
		border-radius: 50%;
		color: #a78bfa;
	}

	h1 {
		font-size: 3rem;
		font-weight: 700;
		color: #f1f5f9;
		margin-bottom: 1rem;
		letter-spacing: -0.02em;
	}

	.subtitle {
		font-size: 1.25rem;
		color: #cbd5e1;
		margin-bottom: 3rem;
		line-height: 1.6;
	}

	.placeholder {
		background: rgba(30, 41, 59, 0.5);
		border: 1px solid rgba(148, 163, 184, 0.1);
		border-radius: 0.75rem;
		padding: 3rem 2rem;
		margin-bottom: 2rem;
	}

	.coming-soon {
		font-size: 1.5rem;
		font-weight: 600;
		color: #a78bfa;
		margin-bottom: 1rem;
	}

	.temp-message {
		color: #94a3b8;
		font-size: 1.05rem;
	}

	.back-link {
		color: #60a5fa;
		text-decoration: none;
		font-weight: 500;
		transition: color 0.2s;
	}

	.back-link:hover {
		color: #93c5fd;
	}

	@media (max-width: 768px) {
		h1 {
			font-size: 2rem;
		}

		.subtitle {
			font-size: 1.05rem;
		}
	}
</style>
