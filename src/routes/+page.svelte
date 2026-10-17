<script>
	let menuOpen = $state(false);
	let openFaq = $state(0);

	const packages = [
		{
			number: '01',
			name: 'Secarik Pesan',
			price: '27.000',
			description: 'Pesan kecil yang terasa istimewa.',
			features: ['Animasi lembut', 'Kartu ucapan digital', 'Hingga 5 foto'],
			className: 'package-soft',
			button: 'Pilih Little Note'
		},
		{
			number: '02',
			name: 'Surat Istimewa',
			price: '30.000',
			description: 'Kejutan manis dengan ruang rahasia.',
			features: ['Login sesuai request', 'Animasi lembut', 'Kartu ucapan digital', 'Hingga 7 foto'],
			className: 'package-lilac',
			button: 'Pilih Secret Garden'
		},
		{
			number: '03',
			name: 'Kotak Kenangan',
			price: '40.000',
			description: 'Cerita yang punya awal dan akhir.',
			features: ['Login sesuai request', 'Animasi lembut', 'Kartu ucapan digital', 'Hingga 7 foto', 'Musik pilihanmu', 'Ending spesial'],
			className: 'package-peach',
			button: 'Pilih Afterglow'
		},
		{
			number: '04',
			name: 'Dunia Kita',
			price: '70.000',
			previousPrice: '80.000',
			description: 'Satu dunia kecil, sepenuhnya milikmu.',
			features: ['Login sesuai request', 'Animasi & maskot', 'Kartu ucapan + card', 'Foto dan video', 'Mini game interaktif', 'Spreadsheet', 'Musik & ending spesial'],
			className: 'package-featured',
			button: 'Pilih paket lengkap'
		}
	];

	const services = [
		{ icon: '♡', title: 'Website ucapan', text: 'Surat digital yang hangat untuk ulang tahun, anniversary, atau hari spesial.' },
		{ icon: '✳', title: 'Confess website', text: 'Ungkapkan perasaan dengan cara yang personal, manis, dan berkesan.' },
		{ icon: '✧', title: 'Digital gift', text: 'Hadiah online dengan foto, musik, animasi, dan detail yang kamu pilih.' },
		{ icon: '⌘', title: 'Custom website', text: 'Punya ide di luar paket? Ceritakan saja, kita wujudkan bersama.' }
	];

	const faqs = [
		{
			question: 'Bagaimana cara memesan?',
			answer: 'Pilih paket yang kamu suka, lalu hubungi kami lewat WhatsApp. Ceritakan konsep, isi, dan detail yang ingin dimasukkan. Setelah semuanya disepakati, kami mulai membuat website-mu.'
		},
		{
			question: 'Apakah desain dan isi website bisa request?',
			answer: 'Bisa! Kamu bisa request tema, warna, teks, musik, gaya login, dan detail lainnya. Fitur mengikuti paket yang dipilih; request khusus di luar paket bisa didiskusikan dulu.'
		},
		{
			question: 'Apa maksud batas jumlah foto?',
			answer: 'Paket 1 mencakup maksimal 5 foto. Paket 2 dan 3 mencakup maksimal 7 foto. Paket 4 mencakup foto dan video; jumlah serta detail kontennya kita sepakati saat konsultasi.'
		},
		{
			question: 'Berapa lama proses pengerjaannya?',
			answer: 'Waktu pengerjaan disesuaikan dengan konsep, kelengkapan bahan, dan fitur yang dipilih. Estimasi akan kami konfirmasi setelah detail pesanan dibicarakan.'
		}
	];

	function orderLink(packageName = '') {
		const message = packageName
			? `Halo Noirelle.Studio! Aku tertarik memesan paket ${packageName}. Boleh tanya-tanya dulu?`
			: 'Halo Noirelle.Studio! Aku ingin konsultasi website custom.';
		return `https://wa.me/?text=${encodeURIComponent(message)}`;
	}
</script>

<svelte:head>
	<title>Noirelle.Studio — Every Idea Deserves a Website</title>
	<meta
		name="description"
		content="Jasa pembuatan website custom untuk ucapan, confess, dan digital gift. Wujudkan ide spesialmu mulai dari Rp27.000."
	/>
	<meta name="theme-color" content="#f8f6f2" />
</svelte:head>

<header class="site-header">
	<a class="wordmark" href="#home" aria-label="Noirelle Studio, beranda">
		<span class="wordmark-mark">n.</span>
		<span>Noirelle<span class="wordmark-light">.Studio</span></span>
	</a>

	<button
		class="menu-toggle"
		aria-label={menuOpen ? 'Tutup menu' : 'Buka menu'}
		aria-expanded={menuOpen}
		onclick={() => (menuOpen = !menuOpen)}
	>
		<span></span><span></span>
	</button>

	<nav class:nav-open={menuOpen} aria-label="Navigasi utama">
		<a href="#layanan" onclick={() => (menuOpen = false)}>Layanan</a>
		<a href="#paket" onclick={() => (menuOpen = false)}>Paket</a>
		<a href="#proses" onclick={() => (menuOpen = false)}>Cara pesan</a>
		<a href="#faq" onclick={() => (menuOpen = false)}>FAQ</a>
		<a class="nav-cta" href={orderLink()} target="_blank" rel="noreferrer">Yuk, ngobrol <span>↗</span></a>
	</nav>
</header>

<main>
	<section class="hero section-wrap" id="home">
		<div class="hero-copy">
			<div class="eyebrow"><span class="eyebrow-dot"></span> CREATIVE WEBSITE SERVICE</div>
			<h1>Idemu pantas<br />punya <em>rumah.</em></h1>
			<p class="hero-description">
				Kami mengubah cerita, perasaan, dan ide kecilmu jadi website custom yang terasa begitu kamu.
			</p>
			<div class="hero-actions">
				<a class="button button-dark" href="#paket">Temukan paketmu <span>↗</span></a>
				<a class="text-link" href="#layanan">Jelajahi layanan <span>↓</span></a>
			</div>
			<div class="hero-note"><span class="note-star">✳</span> Personal by design. Made with feeling.</div>
		</div>

		<div class="hero-art" aria-label="Ilustrasi pratinjau website kartu ucapan digital">
			<div class="orbit orbit-one"></div>
			<div class="orbit orbit-two"></div>
			<div class="sparkle sparkle-one">✳</div>
			<div class="sparkle sparkle-two">✦</div>
			<div class="sparkle sparkle-three">✧</div>
			<div class="art-caption caption-top">a little something<br />made just for you</div>
			<div class="browser-card">
				<div class="browser-top">
					<div class="browser-dots"><i></i><i></i><i></i></div>
					<span>for-you.noirelle.site</span>
					<span class="browser-menu">···</span>
				</div>
				<div class="browser-content">
					<div class="tiny-label">A NOTE FROM THE HEART</div>
					<div class="preview-flower">✿</div>
					<div class="preview-script">you make<br />ordinary days<br /><em>feel like magic</em></div>
					<div class="preview-line"></div>
					<div class="preview-small">made with all my love</div>
					<div class="preview-button">open your letter <span>↗</span></div>
				</div>
			</div>
			<div class="art-caption caption-bottom">your story,<br />beautifully told.</div>
			<div class="floating-sticker">for<br />someone<br /><em>special</em> ♡</div>
		</div>
		<a class="scroll-cue" href="#layanan"><span></span> SCROLL TO EXPLORE</a>
	</section>

	<div class="marquee" aria-label="Website ucapan, confess, digital gift, custom website">
		<div class="marquee-track">
			{#each Array(2) as _}
				<span>WEBSITE UCAPAN</span><b>✳</b><span>CONFESS WEBSITE</span><b>✳</b><span>DIGITAL GIFT</span><b>✳</b><span>CUSTOM WEBSITE</span><b>✳</b>
			{/each}
		</div>
	</div>

	<section class="services section-wrap" id="layanan">
		<div class="section-heading">
			<div>
				<div class="eyebrow">SMALL IDEA, BIG FEELING</div>
				<h2>Lebih dari sekadar<br /><em>sebuah website.</em></h2>
			</div>
			<p>Setiap detail dibuat untuk menyampaikan sesuatu yang mungkin sulit diucapkan langsung.</p>
		</div>
		<div class="service-grid">
			{#each services as service, index}
				<article class="service-card">
					<div class="service-top"><span class="service-number">0{index + 1}</span><span class="service-icon">{service.icon}</span></div>
					<h3>{service.title}</h3>
					<p>{service.text}</p>
					<span class="service-arrow">↗</span>
				</article>
			{/each}
		</div>
		<div class="service-footnote"><span>✳</span> Dari ide paling sederhana sampai kejutan paling lengkap — semuanya bisa jadi milikmu.</div>
	</section>

	<section class="pricing-section" id="paket">
		<div class="section-wrap pricing-inner">
			<div class="section-heading pricing-heading">
				<div>
					<div class="eyebrow">PICK YOUR LITTLE UNIVERSE</div>
					<h2>Hal spesialmu,<br /><em>mulai dari sini.</em></h2>
				</div>
				<p>Empat cara untuk membuat seseorang tersenyum. Pilih yang paling cocok dengan ceritamu.</p>
			</div>
			<div class="pricing-grid">
				{#each packages as item}
					<article class={`package-card ${item.className}`}>
						{#if item.previousPrice}<div class="discount-ribbon">SPECIAL PRICE · HEMAT 10K</div>{/if}
						<div class="package-topline"><span>NOIRELLE / {item.number}</span><span class="package-sparkle">✳</span></div>
						<div class="package-name">{item.name}</div>
						<p class="package-description">{item.description}</p>
						<div class="price-row">
							<span class="currency">Rp</span><span class="price">{item.price}</span>
							{#if item.previousPrice}<del>Rp {item.previousPrice}</del>{/if}
						</div>
						<div class="price-caption">sekali bayar · website personal</div>
						<div class="package-divider"></div>
						<ul class="feature-list">
							{#each item.features as feature}
								<li><span>✳</span>{feature}</li>
							{/each}
						</ul>
						<a
							class:button-light={item.className === 'package-featured'}
							class="button package-button"
							href={orderLink(item.name)}
							target="_blank"
							rel="noreferrer"
						>{item.button}<span>↗</span></a>
					</article>
				{/each}
			</div>
			<p class="pricing-note"><span>♡</span> Semua paket bisa dibicarakan dulu. Fitur tambahan dan request khusus? Tanya saja, ya.</p>
		</div>
	</section>

	<section class="process section-wrap" id="proses">
		<div class="process-intro">
			<div class="eyebrow">FROM YOUR MIND TO YOUR SCREEN</div>
			<h2>Gampang kok,<br /><em>dibuat bareng.</em></h2>
			<p>Nggak perlu paham coding. Kamu bawa ceritanya, kami bantu wujudkan.</p>
			<a class="text-link" href={orderLink()} target="_blank" rel="noreferrer">Mulai konsultasi <span>↗</span></a>
		</div>
		<div class="process-steps">
			<div class="process-step"><span class="step-number">01</span><div><h3>Ceritakan idemu</h3><p>Pilih paket lalu bagikan konsep, pesan, dan detail yang kamu inginkan.</p></div><span class="step-icon">♡</span></div>
			<div class="process-step"><span class="step-number">02</span><div><h3>Racik bersama</h3><p>Kirim bahan seperti foto, teks, atau musik. Kita sepakati tampilan dan isi.</p></div><span class="step-icon">✳</span></div>
			<div class="process-step"><span class="step-number">03</span><div><h3>Jadi kejutan!</h3><p>Website personalmu siap dibagikan dan jadi kenangan yang manis.</p></div><span class="step-icon">✧</span></div>
		</div>
	</section>

	<section class="faq-section" id="faq">
		<div class="section-wrap faq-layout">
			<div class="faq-title">
				<div class="eyebrow">A FEW LITTLE DETAILS</div>
				<h2>Ada yang<br /><em>ingin ditanya?</em></h2>
				<p>Belum menemukan jawabanmu? <a href={orderLink()} target="_blank" rel="noreferrer">Yuk, ngobrol langsung ↗</a></p>
			</div>
			<div class="faq-list">
				{#each faqs as faq, index}
					<div class:faq-open={openFaq === index} class="faq-item">
						<button class="faq-question" aria-expanded={openFaq === index} onclick={() => (openFaq = openFaq === index ? -1 : index)}>
							<span>{faq.question}</span><span class="faq-plus">{openFaq === index ? '−' : '+'}</span>
						</button>
						{#if openFaq === index}<p class="faq-answer">{faq.answer}</p>{/if}
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section class="final-cta section-wrap">
		<div class="cta-deco cta-deco-left">✳</div><div class="cta-deco cta-deco-right">✧</div>
		<div class="eyebrow">SOMETHING SPECIAL STARTS HERE</div>
		<h2>Punya ide kecil<br />yang <em>berarti besar?</em></h2>
		<p>Ceritakan ke kami. Barangkali, sebentar lagi ia punya rumah sendiri di internet.</p>
		<a class="button button-dark" href={orderLink()} target="_blank" rel="noreferrer">Ceritakan idemu <span>↗</span></a>
		<div class="cta-scribble">can't wait to see it ♡</div>
	</section>
</main>

<footer class="site-footer">
	<a class="wordmark footer-wordmark" href="#home"><span class="wordmark-mark">n.</span><span>Noirelle<span class="wordmark-light">.Studio</span></span></a>
	<p>Every idea deserves a website.</p>
	<div class="footer-bottom"><span>© 2026 Noirelle.Studio</span><a href="#home">Made with feeling <span>♡</span></a><a href="#home">Back to top ↑</a></div>
</footer>

<style>
	:global(*) { box-sizing: border-box; }
	:global(html) { scroll-behavior: smooth; scroll-padding-top: 90px; }
	:global(body) { margin: 0; background: #f8f6f2; color: #26231f; font-family: 'DM Sans', 'Avenir Next', Avenir, sans-serif; -webkit-font-smoothing: antialiased; }
	:global(body)::selection { background: #e9b8a8; color: #26231f; }
	:global(a) { color: inherit; text-decoration: none; }
	:global(button) { font: inherit; }
	:global(.section-wrap) { width: min(1160px, calc(100% - 96px)); margin-inline: auto; }
	.site-header { height: 84px; width: min(1320px, calc(100% - 96px)); margin: auto; display: flex; align-items: center; justify-content: space-between; position: relative; z-index: 5; border-bottom: 1px solid #e9e5df; }
	.wordmark { display: inline-flex; align-items: center; gap: 10px; font-family: Georgia, serif; font-size: 20px; letter-spacing: -.8px; font-weight: 600; }
	.wordmark-mark { width: 31px; height: 31px; display: grid; place-items: center; border-radius: 50%; background: #29251f; color: #f8f6f2; font-size: 16px; font-style: italic; }
	.wordmark-light { font-weight: 400; color: #8a8178; }
	.site-header nav { display: flex; align-items: center; gap: 38px; font-size: 12px; color: #68615a; }
	.site-header nav a { transition: color .2s ease; }
	.site-header nav a:hover { color: #a56f62; }
	.site-header nav .nav-cta { padding: 12px 17px; border: 1px solid #d8d1c9; border-radius: 3px; color: #2e2925; }
	.nav-cta span { margin-left: 12px; }
	.menu-toggle { display: none; }
	.hero { min-height: 650px; display: grid; grid-template-columns: 1fr 1fr; align-items: center; position: relative; padding-top: 28px; padding-bottom: 76px; }
	.hero-copy { padding: 24px 0 38px 4.5%; position: relative; z-index: 1; }
	.eyebrow { color: #9a776a; font-size: 9px; letter-spacing: 2px; font-weight: 600; }
	.eyebrow-dot { width: 6px; height: 6px; border-radius: 50%; background: #cf9684; display: inline-block; margin: 0 8px 1px 0; }
	h1, h2, h3, p { margin-top: 0; }
	.hero h1 { font: 400 clamp(58px, 6.6vw, 88px)/.99 Georgia, 'Times New Roman', serif; letter-spacing: -4px; margin: 26px 0 24px; }
	h1 em, h2 em { font-weight: 400; color: #b77f70; }
	.hero-description { color: #777068; max-width: 390px; font-size: 14px; line-height: 1.9; margin-bottom: 29px; }
	.hero-actions { display: flex; align-items: center; gap: 25px; }
	.button { display: inline-flex; align-items: center; justify-content: space-between; gap: 25px; padding: 15px 18px; font-size: 11px; transition: transform .2s ease, background .2s ease; }
	.button:hover { transform: translateY(-2px); }
	.button-dark { color: #fffaf4; background: #2d2924; }
	.button-dark:hover { background: #54453e; }
	.button span { font-size: 15px; }
	.text-link { color: #514942; font-size: 11px; border-bottom: 1px solid #c9bdb1; padding: 5px 0; }
	.text-link span { margin-left: 8px; }
	.hero-note { margin-top: 58px; color: #948a80; font: italic 12px Georgia, serif; }
	.note-star { color: #c18778; font-size: 17px; margin-right: 9px; }
	.hero-art { position: relative; height: 490px; display: grid; place-items: center; }
	.orbit { position: absolute; border: 1px solid #e8ddd4; border-radius: 50%; }
	.orbit-one { width: 440px; height: 440px; }
	.orbit-two { width: 510px; height: 510px; border-style: dashed; border-color: #ece5dd; }
	.browser-card { position: relative; z-index: 1; width: 305px; height: 372px; background: #fffdfa; box-shadow: 0 24px 55px #5b45351a; transform: rotate(3deg); }
	.browser-top { height: 31px; border-bottom: 1px solid #f0ece6; display: flex; align-items: center; padding: 0 11px; color: #b1a8a0; font-size: 7px; letter-spacing: .2px; }
	.browser-dots { display: flex; gap: 3px; margin-right: auto; }
	.browser-dots i { width: 4px; height: 4px; background: #e3b9ad; border-radius: 50%; }
	.browser-dots i:nth-child(2) { background: #e7d3a7; }.browser-dots i:nth-child(3) { background: #bdc9ad; }
	.browser-menu { margin-left: auto; font-size: 13px; }
	.browser-content { height: calc(100% - 31px); background: linear-gradient(154deg,#fcf5ed,#f4e5dc 62%,#ead1c7); display: flex; flex-direction: column; align-items: center; padding-top: 27px; overflow: hidden; position: relative; }
	.browser-content::after { content: ''; position: absolute; width: 245px; height: 245px; border: 1px solid #fff8f0aa; border-radius: 50%; bottom: -110px; }
	.tiny-label { color: #9e7970; font-size: 6px; letter-spacing: 2px; }
	.preview-flower { color: #bd8275; font-size: 34px; margin-top: 20px; }
	.preview-script { text-align: center; font: 29px/1.12 Georgia, serif; letter-spacing: -.9px; color: #51403b; margin-top: 8px; }
	.preview-script em { color: #ab6f63; }
	.preview-line { width: 34px; border-top: 1px solid #bb9185; margin-top: 17px; }
	.preview-small { color: #987e73; margin-top: 11px; font: italic 9px Georgia,serif; }
	.preview-button { margin-top: 19px; border: 1px solid #ba9388; border-radius: 30px; color: #735951; padding: 8px 14px; font: 8px Georgia,serif; }
	.preview-button span { margin-left: 11px; }
	.sparkle { position: absolute; color: #bd8f80; z-index: 2; }
	.sparkle-one { top: 90px; left: 14%; font-size: 22px; }
	.sparkle-two { top: 133px; right: 7%; font-size: 20px; color: #a7ad91; }
	.sparkle-three { bottom: 88px; left: 17%; font-size: 27px; color: #d3ae7e; }
	.art-caption { position: absolute; z-index: 2; color: #8c8178; font: italic 12px/1.5 Georgia,serif; }
	.caption-top { top: 33px; right: 1%; transform: rotate(8deg); }
	.caption-bottom { bottom: 32px; left: 2%; transform: rotate(-8deg); }
	.floating-sticker { position: absolute; z-index: 3; right: 1%; bottom: 67px; width: 76px; height: 76px; border-radius: 50%; background: #d5b99e; color: #554841; display: grid; place-content: center; text-align: center; font: 10px/1.25 Georgia,serif; transform: rotate(9deg); box-shadow: 0 7px 20px #5b45351a; }
	.floating-sticker em { color: #855e51; }
	.scroll-cue { position: absolute; left: 4.5%; bottom: 27px; font-size: 8px; letter-spacing: 1.7px; color: #9a9189; display: flex; align-items: center; gap: 10px; }
	.scroll-cue span { width: 30px; height: 1px; background: #c9bcb0; }
	.marquee { height: 59px; background: #ede7df; overflow: hidden; display: flex; align-items: center; }
	.marquee-track { width: max-content; display: flex; align-items: center; gap: 31px; animation: drift 36s linear infinite; color: #776e65; white-space: nowrap; }
	.marquee-track span { font-size: 9px; letter-spacing: 2px; }
	.marquee-track b { color: #bd8374; font-size: 14px; font-weight: 400; }
	@keyframes drift { to { transform: translateX(-50%); } }
	.services { padding-top: 113px; padding-bottom: 110px; }
	.section-heading { display: flex; justify-content: space-between; align-items: end; margin-bottom: 48px; }
	.section-heading h2, .process h2, .faq-title h2, .final-cta h2 { font: 400 clamp(38px, 4.3vw, 55px)/1.08 Georgia,serif; letter-spacing: -1.8px; margin: 18px 0 0; }
	.section-heading > p { width: 280px; color: #827970; font-size: 12px; line-height: 1.9; margin: 0 2% 4px 20px; }
	.service-grid { display: grid; grid-template-columns: repeat(4,1fr); border-top: 1px solid #e5dfd7; border-bottom: 1px solid #e5dfd7; }
	.service-card { padding: 25px 24px 28px 0; min-height: 210px; position: relative; border-right: 1px solid #e5dfd7; }
	.service-card:not(:first-child) { padding-left: 25px; }
	.service-card:last-child { border-right: 0; }
	.service-top { display: flex; justify-content: space-between; align-items: center; }
	.service-number { color: #a49a90; font-size: 9px; letter-spacing: 1px; }
	.service-icon { width: 32px; height: 32px; display: grid; place-items: center; border: 1px solid #e2d5cb; border-radius: 50%; color: #b17b6e; font-size: 15px; }
	.service-card h3 { font: 400 18px Georgia,serif; margin: 24px 0 10px; }
	.service-card p { font-size: 11px; line-height: 1.8; color: #898078; max-width: 205px; margin: 0; }
	.service-arrow { position: absolute; right: 20px; bottom: 24px; color: #ad9b8c; font-size: 13px; }
	.service-footnote { text-align: center; margin-top: 30px; font: italic 12px Georgia,serif; color: #8c8279; }
	.service-footnote span { color: #bd8275; margin-right: 8px; }
	.pricing-section { background: #f0ebe4; padding: 106px 0 94px; }
	.pricing-heading { margin-bottom: 43px; }
	.pricing-grid { display: grid; grid-template-columns: repeat(4,1fr); gap: 13px; align-items: stretch; }
	.package-card { background: #fbfaf7; min-height: 416px; padding: 23px 19px 19px; display: flex; flex-direction: column; position: relative; border: 1px solid #e8e2da; }
	.package-lilac { background: #f8f5f7; }.package-peach { background: #fcf6f1; }
	.package-featured { background: #2d2925; border-color: #2d2925; color: #fffaf4; }
	.package-topline { font-size: 8px; letter-spacing: 1.5px; color: #9a8f84; display: flex; justify-content: space-between; align-items: center; }
	.package-featured .package-topline { color: #c7b5a4; }
	.package-sparkle { color: #bd8172; font-size: 14px; }
	.package-featured .package-sparkle { color: #e2b49f; }
	.package-name { font: 400 22px Georgia,serif; margin-top: 29px; letter-spacing: -.5px; }
	.package-description { min-height: 30px; margin: 7px 0 17px; font-size: 10px; color: #8c837a; line-height: 1.6; }
	.package-featured .package-description { color: #c6bcb2; }
	.price-row { display: flex; align-items: baseline; gap: 3px; white-space: nowrap; }
	.currency { font-size: 12px; color: #937a6c; }
	.price { font: 400 35px Georgia,serif; letter-spacing: -1.8px; }
	.package-featured .currency { color: #dfb5a3; }
	.price-row del { color: #a99e92; font-size: 10px; margin-left: 5px; }
	.price-caption { color: #a0978d; font-size: 8px; margin-top: 3px; }
	.package-featured .price-caption { color: #b8aca1; }
	.package-divider { height: 1px; background: #e9e3dc; margin: 17px 0 13px; }
	.package-featured .package-divider { background: #514943; }
	.feature-list { list-style: none; padding: 0; margin: 0 0 20px; display: grid; gap: 9px; color: #6e675f; font-size: 10px; line-height: 1.35; }
	.package-featured .feature-list { color: #e1d8cf; }
	.feature-list li { display: flex; gap: 8px; align-items: baseline; }
	.feature-list li span { color: #bb8172; font-size: 9px; }
	.package-button { margin-top: auto; border: 1px solid #d9d1c8; color: #4d453e; width: 100%; padding: 12px 12px; font-size: 10px; }
	.package-button:hover { background: #f1e9e1; }
	.package-featured .package-button { border-color: #e7d0c2; background: #f3e6dc; color: #342a26; }
	.package-featured .package-button:hover { background: #fff2e8; }
	.discount-ribbon { position: absolute; top: -10px; right: 11px; padding: 5px 9px; background: #cf9885; color: white; font-size: 7px; letter-spacing: 1px; }
	.pricing-note { text-align: center; margin: 27px 0 0; font-size: 10px; color: #82786f; }
	.pricing-note span { color: #b98072; margin-right: 6px; }
	.process { padding-top: 117px; padding-bottom: 117px; display: grid; grid-template-columns: .8fr 1.2fr; gap: 12%; align-items: center; }
	.process-intro h2 { margin-bottom: 17px; }
	.process-intro > p { max-width: 280px; font-size: 12px; line-height: 1.9; color: #837970; margin-bottom: 21px; }
	.process-steps { border-top: 1px solid #e6dfd7; }
	.process-step { border-bottom: 1px solid #e6dfd7; display: grid; grid-template-columns: 39px 1fr 32px; gap: 13px; align-items: center; padding: 23px 0; }
	.step-number { color: #b18173; font: italic 13px Georgia,serif; }
	.process-step h3 { font: 400 17px Georgia,serif; margin: 0 0 7px; }
	.process-step p { color: #898078; font-size: 10px; line-height: 1.7; margin: 0; }
	.step-icon { height: 31px; width: 31px; display: grid; place-items: center; border: 1px solid #e6d9ce; border-radius: 50%; color: #b17b6e; }
	.faq-section { padding: 99px 0 108px; background: #eee8e0; }
	.faq-layout { display: grid; grid-template-columns: .85fr 1.15fr; gap: 12%; }
	.faq-title h2 { margin-bottom: 20px; }
	.faq-title > p { color: #867c72; font-size: 11px; line-height: 1.8; }
	.faq-title > p a { color: #9c6d60; border-bottom: 1px solid #c7a99b; }
	.faq-list { border-top: 1px solid #dcd3ca; }
	.faq-item { border-bottom: 1px solid #dcd3ca; }
	.faq-question { width: 100%; padding: 19px 0; background: none; border: 0; display: flex; justify-content: space-between; text-align: left; cursor: pointer; color: #39332e; font: 400 15px Georgia,serif; }
	.faq-plus { font: 400 20px Georgia,serif; color: #a77b6e; padding-left: 20px; }
	.faq-answer { font-size: 11px; line-height: 1.9; color: #7d746b; padding: 0 26px 19px 0; margin: -2px 0 0; max-width: 500px; }
	.final-cta { text-align: center; padding-top: 112px; padding-bottom: 115px; position: relative; overflow: hidden; }
	.final-cta h2 { margin: 17px 0; }
	.final-cta > p { color: #837970; font-size: 12px; line-height: 1.8; max-width: 400px; margin: 0 auto 24px; }
	.final-cta .button { margin: 0 auto; }
	.cta-deco { position: absolute; color: #c69a88; }
	.cta-deco-left { font-size: 48px; top: 125px; left: 17%; transform: rotate(-14deg); }
	.cta-deco-right { font-size: 44px; bottom: 97px; right: 18%; color: #a4a88e; }
	.cta-scribble { color: #a88c7c; font: italic 12px Georgia,serif; position: absolute; right: 21%; top: 176px; transform: rotate(8deg); }
	.site-footer { border-top: 1px solid #e5dfd7; padding: 26px max(48px, calc((100% - 1160px)/2)) 18px; display: grid; grid-template-columns: 1fr 1fr; align-items: center; }
	.footer-wordmark { font-size: 17px; }
	.footer-wordmark .wordmark-mark { width: 27px; height: 27px; font-size: 14px; }
	.site-footer > p { justify-self: end; color: #988e84; font: italic 12px Georgia,serif; margin: 0; }
	.footer-bottom { grid-column: 1/-1; display: flex; justify-content: space-between; border-top: 1px solid #ebe6e0; margin-top: 20px; padding-top: 15px; color: #9a9188; font-size: 9px; }
	.footer-bottom a span { color: #b98072; }
	@media (prefers-reduced-motion: reduce) { :global(html) { scroll-behavior: auto; } *, *::before, *::after { animation-duration: .01ms !important; animation-iteration-count: 1 !important; transition-duration: .01ms !important; } }
	@media (max-width: 900px) {
		:global(.section-wrap) { width: min(100% - 56px, 720px); }
		.site-header { width: calc(100% - 56px); height: 72px; }
		.site-header nav { gap: 21px; }
		.hero { min-height: 580px; }
		.hero-copy { padding-left: 0; }
		.hero h1 { font-size: clamp(57px, 8vw, 76px); }
		.hero-art { transform: scale(.83); }
		.scroll-cue { left: 0; }
		.pricing-grid { grid-template-columns: repeat(2,1fr); gap: 16px; }
		.package-card { min-height: 390px; padding: 24px; }
		.process, .faq-layout { gap: 7%; }
		.cta-deco-left { left: 8%; }.cta-deco-right { right: 9%; }.cta-scribble { right: 12%; }
	}
	@media (max-width: 640px) {
		:global(.section-wrap) { width: calc(100% - 42px); }
		.site-header { width: calc(100% - 42px); height: 68px; }
		.wordmark { font-size: 18px; }
		.menu-toggle { display: flex; width: 38px; height: 38px; border: 1px solid #e5ded6; background: transparent; flex-direction: column; justify-content: center; gap: 5px; align-items: center; }
		.menu-toggle span { height: 1px; width: 15px; background: #433c36; }
		.site-header nav { display: none; position: absolute; left: -21px; right: -21px; top: 68px; padding: 18px 21px 22px; background: #f8f6f2; border-bottom: 1px solid #e5dfd7; flex-direction: column; align-items: stretch; gap: 0; }
		.site-header nav.nav-open { display: flex; }
		.site-header nav a { padding: 13px 0; border-bottom: 1px solid #eee9e2; }
		.site-header nav .nav-cta { margin-top: 11px; padding: 12px 14px; }
		.hero { grid-template-columns: 1fr; padding-top: 53px; padding-bottom: 63px; min-height: 0; }
		.hero-copy { padding: 0; }
		.hero h1 { font-size: clamp(60px, 15vw, 82px); letter-spacing: -3.5px; margin: 23px 0 18px; }
		.hero-description { font-size: 13px; max-width: 340px; margin-bottom: 23px; }
		.hero-actions { gap: 17px; }
		.button { gap: 17px; }
		.hero-note { margin-top: 27px; }
		.hero-art { height: 420px; margin: 5px -28px -4px; transform: scale(.82); }
		.orbit-one { width: 385px; height: 385px; }.orbit-two { width: 440px; height: 440px; }
		.browser-card { width: 270px; height: 330px; }
		.browser-content { padding-top: 20px; }
		.preview-script { font-size: 26px; }
		.caption-top { right: 0; top: 17px; }.caption-bottom { bottom: 15px; left: 1%; }
		.floating-sticker { right: 1%; bottom: 38px; width: 68px; height: 68px; }
		.scroll-cue { bottom: 20px; }
		.marquee { height: 49px; }
		.services { padding-top: 78px; padding-bottom: 76px; }
		.section-heading { display: block; margin-bottom: 30px; }
		.section-heading h2, .process h2, .faq-title h2, .final-cta h2 { font-size: 43px; }
		.section-heading > p { width: auto; max-width: 340px; margin: 18px 0 0; }
		.service-grid { grid-template-columns: repeat(2,1fr); }
		.service-card { min-height: 190px; padding: 19px 12px 21px 0; border-bottom: 1px solid #e5dfd7; }
		.service-card:not(:first-child) { padding-left: 14px; }
		.service-card:nth-child(2) { border-right: 0; }
		.service-card:nth-child(3), .service-card:nth-child(4) { border-bottom: 0; }
		.service-card h3 { font-size: 17px; margin-top: 20px; }
		.service-card p { font-size: 10px; }
		.service-arrow { right: 9px; bottom: 17px; }
		.service-footnote { font-size: 11px; line-height: 1.7; }
		.pricing-section { padding: 78px 0 67px; }
		.pricing-heading { margin-bottom: 29px; }
		.pricing-grid { grid-template-columns: 1fr; gap: 15px; }
		.package-card { min-height: 0; padding: 23px 21px 20px; }
		.package-name { margin-top: 20px; }
		.package-description { min-height: 0; margin-bottom: 13px; }
		.price { font-size: 38px; }
		.package-divider { margin: 14px 0 13px; }
		.feature-list { grid-template-columns: 1fr 1fr; gap: 10px 8px; margin-bottom: 20px; }
		.package-featured .feature-list { grid-template-columns: 1fr 1fr; }
		.package-button { margin-top: 5px; }
		.pricing-note { font-size: 10px; line-height: 1.7; }
		.process { padding-top: 78px; padding-bottom: 78px; display: block; }
		.process-intro { margin-bottom: 35px; }
		.process-intro > p { max-width: 320px; }
		.process-step { grid-template-columns: 30px 1fr 30px; gap: 10px; padding: 19px 0; }
		.process-step h3 { font-size: 16px; }
		.process-step p { font-size: 10px; }
		.faq-section { padding: 75px 0 78px; }
		.faq-layout { display: block; }
		.faq-title { margin-bottom: 30px; }
		.faq-title h2 { margin-bottom: 14px; }
		.faq-question { font-size: 14px; }
		.faq-answer { font-size: 10px; }
		.final-cta { padding-top: 80px; padding-bottom: 82px; }
		.final-cta h2 { font-size: 42px; }
		.final-cta > p { font-size: 11px; max-width: 320px; }
		.cta-deco-left { top: 45px; left: 5%; font-size: 30px; }.cta-deco-right { right: 6%; bottom: 42px; font-size: 30px; }.cta-scribble { top: auto; right: 8%; bottom: 39px; font-size: 10px; }
		.site-footer { padding: 23px 21px 16px; grid-template-columns: 1fr; gap: 10px; }
		.site-footer > p { justify-self: start; }
		.footer-bottom { grid-column: 1; flex-wrap: wrap; gap: 12px; margin-top: 8px; }
	}
</style>
