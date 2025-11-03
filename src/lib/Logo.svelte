<script lang="ts">
	let { height, variant, width }: { height: number; variant: 'normal' | 'short' | 'selector'; width?: number } = $props();

	let kilo: string;
	let joule: string;
	let endpoint: number;
	let jouleX: number;
        let strokeWidth: number = 20;

	if (variant === 'normal') {
		kilo = 'kilo';
		joule = 'Joule';
		endpoint = 750;
		jouleX = 360;
	} else {
		kilo = 'k';
		joule = 'J';
		endpoint = 250;
                jouleX = 185;
	}

        if (variant === 'selector') {
                kilo = '';
                joule = '';
                strokeWidth = 10;
                endpoint = width - 10;
        }
</script>

<div id="logo" style="height: {height}px;">
	<svg width="100%" height="100%" viewBox="0 0 {endpoint+10} 160" xmlns="http://www.w3.org/2000/svg">
		<!-- Text: "kilo" or "k" -->
		<text
			x="100"
			y="150"
			font-family="Arial, sans-serif"
			font-weight="700"
			font-size="150"
			fill="rgb(144,144,144)"
		>
			{kilo}
		</text>

		<!-- Text: "Joule" or "J" -->
		<text
			x="{jouleX}"
			y="150"
			font-family="Arial, sans-serif"
			font-weight="700"
			font-size="150"
			fill="rgb(90,90,90)"
		>
			{joule}
		</text>

		<!-- Curved line with gradient -->
		<path
			d="M 10 60 L 30 60 L 60 150 L 80 10 L {endpoint} 10"
			fill="none"
			stroke="url(#gradient)"
			stroke-width="{strokeWidth}"
			stroke-linecap="round"
			stroke-linejoin="round"
		/>

		<!-- Gradient definition -->
		<defs>
			<linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="0%">
				<stop offset="0%" stop-color="rgb(135,93,249)" />
				<stop offset="100%" stop-color="rgb(50,139,255)" />
			</linearGradient>
		</defs>
	</svg>
</div>

<style>
	#logo {
		display: flex;
	}
</style>
