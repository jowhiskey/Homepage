<script lang="ts">
	import { Calculator, Zap, Check, TrendingUp, ChevronDown } from '@lucide/svelte';

	function scrollToEditor() {
		document.getElementById('editor-demo')?.scrollIntoView({ behavior: 'smooth' });
	}
</script>

<div class="landing-page">
	<!-- Hero Section -->
	<section class="hero">
		<div class="hero-container">
			<div class="hero-content">
				<h1 class="hero-title">
					Engineering,
					<span class="gradient-text">Without Friction</span>
				</h1>
				<p class="hero-description">
					kiloJoule is a modern Computer Algebra System designed for engineers. Track units
					automatically, perform complex calculations intuitively, and collaborate seamlessly—all in a
					beautiful, modern interface.
				</p>
				<div class="hero-cta">
					<a href="/waitlist" class="cta-primary">Start for free</a>
					<a href="/docs" class="cta-secondary">
						<Calculator size={20} />
						View Documentation
					</a>
				</div>
			</div>

			<div class="hero-image-container">
				<img src="/hero-screenshot.png" alt="kiloJoule interface" class="hero-image" />
			</div>
		</div>

		<button class="try-it-link" on:click={scrollToEditor}>
			Try it out <ChevronDown size={16} />
		</button>
	</section>

	<!-- Interactive Demo Section -->
	<section id="editor-demo" class="demo-section">
		<div class="demo-content">
			<h2 class="section-title">Try It Out</h2>
			<p class="section-description">
				Experience the power of kiloJoule's editor. Start typing to create calculations, add units,
				and see results in real-time.
			</p>
			<div class="editor-container">
			</div>
		</div>
	</section>

	<!-- Problem-Solution Section -->
	<section class="benefits-section">
		<div class="benefits-content">
			<h2 class="section-title">Why kiloJoule?</h2>
			<p class="section-subtitle">
				Traditional engineering software is holding you back. It's time for a modern approach.
			</p>

			<div class="benefits-grid">
				<div class="benefit-card">
					<div class="benefit-icon modern">
						<TrendingUp size={24} />
					</div>
					<h3>Modern Interface</h3>
					<p>
						Forget clunky 1990s interfaces. kiloJoule brings engineering calculations into the modern
						era with an intuitive, streamlined design that feels natural to use.
					</p>
				</div>

				<div class="benefit-card">
					<div class="benefit-icon units">
						<Check size={24} />
					</div>
					<h3>Automatic Unit Tracking</h3>
					<p>
						Never make a unit conversion error again. kiloJoule tracks units automatically throughout
						your calculations, preventing costly mistakes and saving you time.
					</p>
				</div>

				<div class="benefit-card">
					<div class="benefit-icon accessible">
						<Zap size={24} />
					</div>
					<h3>Accessible & Affordable</h3>
					<p>
						Professional engineering tools shouldn't cost thousands. kiloJoule delivers enterprise-grade
						capabilities at a fraction of the price, with no hidden fees or licensing nightmares.
					</p>
				</div>

				<div class="benefit-card">
					<div class="benefit-icon opensource">
						<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
							<circle cx="12" cy="12" r="10"></circle>
							<path d="M12 16v-4"></path>
							<path d="M12 8h.01"></path>
						</svg>
					</div>
					<h3>Open Source</h3>
					<p>
						The math formula editor and page editor are completely open source. No vendor lock-in, no black boxes—just transparent, community-driven tools you can trust and customize.
					</p>
				</div>
			</div>

			<div class="comparison-note">
				<p>
					Tools like MATLAB, Mathematica, and Maple have served engineers for decades—but they were
					built for a different era. Their steep learning curves, outdated interfaces, and
					prohibitive costs create unnecessary barriers to engineering work. kiloJoule takes the best
					of these systems and reimagines them for modern engineers who expect software to be
					powerful, intuitive, and accessible.
				</p>
			</div>
		</div>
	</section>

	<!-- Call to Action Section -->
	<section class="final-cta">
		<div class="final-cta-content">
			<h2>Stop fighting your tools.</h2>
			<p>Engineering software doesn't have to feel like it's from 1995.</p>
			<a href="/waitlist" class="cta-primary large">Join the Waitlist</a>
		</div>
	</section>
</div>

<style>
	.landing-page {
		color: #1e293b;
		min-height: 100vh;
		background: #ffffff;
	}

	/* Hero Section */
	.hero {
		min-height: 100vh;
		padding: 8rem 2rem 2rem;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		position: relative;
		overflow: hidden;
		background: linear-gradient(135deg, #f8fafc 0%, #e0e7ff 100%);
		padding-top: 6rem;
	}

	.hero-container {
		max-width: 1280px;
		width: 100%;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 4rem;
		align-items: center;
		margin-bottom: 3rem;
	}

	.hero-content {
		text-align: left;
		position: relative;
		z-index: 2;
	}

	.hero-title {
		font-size: 3.5rem;
		font-weight: 700;
		line-height: 1.1;
		margin-bottom: 1.5rem;
		letter-spacing: -0.03em;
		color: #0f172a;
		letter-spacing: -0.03em;
		color: #0f172a;
	}

	.gradient-text {
		background: linear-gradient(135deg, #3b82f6, #8b5cf6);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.hero-description {
		font-size: 1.2rem;
		color: #475569;
		line-height: 1.6;
		margin-bottom: 2rem;
		font-weight: 400;
	}

	.hero-cta {
		display: flex;
		gap: 1rem;
		justify-content: flex-start;
		flex-wrap: wrap;
	}

	.hero-image-container {
		position: relative;
		width: 100%;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.hero-image {
		width: 100%;
		height: auto;
		border-radius: 1rem;
		box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
		transform: perspective(1500px) rotateY(-8deg) rotateX(3deg);
		transform-origin: center right;
	}

	.cta-primary {
		background: linear-gradient(135deg, #3b82f6, #2563eb);
		color: white;
		padding: 0.875rem 2rem;
		border-radius: 0.5rem;
		text-decoration: none;
		font-weight: 600;
		font-size: 1.05rem;
		transition: all 0.3s;
		box-shadow: 0 4px 14px rgba(59, 130, 246, 0.4);
	}

	.cta-primary:hover {
		transform: translateY(-2px);
		box-shadow: 0 8px 20px rgba(59, 130, 246, 0.5);
	}

	.cta-primary.large {
		padding: 1rem 2.5rem;
		font-size: 1.125rem;
	}

	.cta-secondary {
		background: rgba(255, 255, 255, 0.9);
		border: 1px solid #e2e8f0;
		color: #475569;
		padding: 0.875rem 2rem;
		border-radius: 0.5rem;
		text-decoration: none;
		font-weight: 600;
		font-size: 1.05rem;
		transition: all 0.3s;
		display: inline-flex;
		align-items: center;
		gap: 0.5rem;
	}

	.cta-secondary:hover {
		background: #ffffff;
		border-color: #cbd5e1;
		transform: translateY(-2px);
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
	}

	.try-it-link {
		background: none;
		border: none;
		color: #64748b;
		font-size: 0.95rem;
		font-weight: 500;
		cursor: pointer;
		transition: all 0.2s;
		display: inline-flex;
		align-items: center;
		gap: 0.25rem;
		font-family: inherit;
		align-self: center;
	}

	.try-it-link:hover {
		color: #3b82f6;
		transform: translateY(2px);
	}

	/* Demo Section */
	.demo-section {
		min-height: 90vh;
		padding: 6rem 2rem;
		background: #ffffff;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	.demo-content {
		max-width: 1100px;
		margin: 0 auto;
	}

	.section-title {
		font-size: 2.5rem;
		font-weight: 700;
		text-align: center;
		margin-bottom: 1rem;
		letter-spacing: -0.02em;
		color: #0f172a;
	}

	.section-description {
		text-align: center;
		color: #64748b;
		font-size: 1.15rem;
		margin-bottom: 4rem;
		max-width: 600px;
		margin-left: auto;
		margin-right: auto;
		line-height: 1.6;
	}

	.editor-container {
		background: #f8fafc;
		border: 1px solid #e2e8f0;
		border-radius: 1rem;
		padding: 3rem;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
		max-width: 900px;
		margin: 0 auto;
		overflow: auto;
		max-height: 70vh;
	}

	/* Benefits Section */
	.benefits-section {
		padding: 6rem 2rem;
		background: #f8fafc;
	}

	.benefits-content {
		max-width: 1100px;
		margin: 0 auto;
	}

	.section-subtitle {
		text-align: center;
		color: #64748b;
		font-size: 1.15rem;
		margin-bottom: 4rem;
		line-height: 1.6;
	}

	.benefits-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 1.5rem;
		margin-bottom: 4rem;
	}

	.benefit-card {
		background: #ffffff;
		border: 1px solid #e2e8f0;
		border-radius: 1rem;
		padding: 2.5rem;
		transition: all 0.3s;
	}

	.benefit-card:hover {
		border-color: #cbd5e1;
		transform: translateY(-2px);
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
	}

	.benefit-icon {
		width: 48px;
		height: 48px;
		border-radius: 0.5rem;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-bottom: 1.25rem;
	}

	.benefit-icon.modern {
		background: #eff6ff;
		color: #3b82f6;
	}

	.benefit-icon.units {
		background: #f5f3ff;
		color: #8b5cf6;
	}

	.benefit-icon.accessible {
		background: #f0fdf4;
		color: #22c55e;
	}

	.benefit-icon.opensource {
		background: #fff7ed;
		color: #f97316;
	}

	.benefit-card h3 {
		font-size: 1.4rem;
		font-weight: 600;
		margin-bottom: 0.75rem;
		color: #0f172a;
	}

	.benefit-card p {
		color: #64748b;
		line-height: 1.7;
		font-size: 0.95rem;
	}

	.comparison-note {
		background: #ffffff;
		border: 1px solid #e2e8f0;
		border-left: 3px solid #3b82f6;
		padding: 2.5rem;
		border-radius: 1rem;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
	}

	.comparison-note p {
		color: #475569;
		line-height: 1.8;
		font-size: 1.05rem;
		margin: 0;
	}

	/* Final CTA Section */
	.final-cta {
		padding: 6rem 2rem;
		background: linear-gradient(135deg, #f8fafc 0%, #e0e7ff 100%);
	}

	.final-cta-content {
		text-align: center;
		max-width: 700px;
		margin: 0 auto;
	}

	.final-cta-content h2 {
		font-size: 2.75rem;
		font-weight: 700;
		margin-bottom: 1rem;
		letter-spacing: -0.02em;
		color: #0f172a;
	}

	.final-cta-content p {
		color: #64748b;
		font-size: 1.2rem;
		margin-bottom: 2.5rem;
	}

	/* Responsive Design */
	@media (max-width: 768px) {
		.hero {
			padding: 8rem 1rem 2rem;
			padding-top: 8rem;
		}

		.hero-container {
			grid-template-columns: 1fr;
			gap: 2rem;
		}

		.hero-content {
			text-align: center;
		}

		.hero-cta {
			justify-content: center;
		}

		.hero-image {
			transform: perspective(1500px) rotateY(0deg) rotateX(0deg) scale(1);
		}

		.hero-title {
			font-size: 2.5rem;
		}

		.section-title {
			font-size: 2rem;
		}

		.benefits-grid {
			grid-template-columns: 1fr;
		}

		.editor-container {
			padding: 1rem;
		}

		.final-cta-content h2 {
			font-size: 2rem;
		}
	}
</style>