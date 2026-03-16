<script>
	let personalInfo = {
		name: 'Luis Quezada',
		title: 'IT Student & Developer',
		email: 'luis@quezada.nl',
		phone: '(929) 595 6327',
		location: 'Staten Island, NY',
		linkedin: 'https://linkedin.com/in/quezada-nl',
		github: 'https://github.com/hypnoticsiege',
		website: 'https://quezada.nl'
	};

	let summary = `Self-taught developer and IT student with hands-on experience in customer-facing technical support, networking fundamentals, and full-stack web development. Comfortable working across different environments, with a track record of solving real problems for real people. From troubleshooting gym equipment connectivity, to building production-ready web platforms.`;

	let experience = [
		{
			title: 'Member Service Representative',
			company: 'Planet Fitness',
			location: 'Staten Island, NY',
			period: '2025 - Present',
			bullets: [
				'Opened the facility solo during early-morning shifts, building a loyal regular crowd that left positive online reviews by name.',
				'Ranked #1 in membership sales multiple months, earning performance bonuses for highest Black Card conversion rate in the location.',
				'Maintained accurate digital and physical records across membership accounts, flagging data inconsistencies and resolving them.',
				'Provided technical support for connected gym equipment, troubleshooting network and hardware issues to minimize downtime.'
			]
		},
		{
			title: 'Sales Associate',
			company: 'T.J. Maxx',
			location: 'Staten Island, NY',
			period: '2024 - 2025',
			bullets: [
				'Managed backroom operations including receiving, sorting, and organizing incoming inventory to keep the sales floor stocked efficiently.',
				'Independently designed and built end-cap and table displays that improved product visibility.',
				'Cross-trained on the register and stepped in during high-traffic periods, demonstrating flexibility.'
			]
		}
	];

	let education = [
		{
			degree: 'Computer Technology (AAS)',
			institution: 'College of Staten Island',
			location: 'Staten Island, NY',
			period: '2025 - Present',
			details: 'Programming · Networking · Database Management'
		},
		{
			degree: 'High School Diploma',
			institution: 'Lavelle Preparatory Charter School',
			location: 'Staten Island, NY',
			period: '2021 - 2025',
			details: 'AP English · Spanish · Pre-Calculus'
		}
	];

	let skills = {
		technical: [
			'Windows & macOS',
			'Linux CLI',
			'FTP & RDP',
			'TCP/IP · DHCP · DNS',
			'Hardware Troubleshooting',
			'TypeScript',
			'Bash',
			'Python',
			'Google Workspace',
			'Printer & Peripheral Setup'
		],
		professional: [
			'Customer Support',
			'Problem Solving',
			'Clear Communicator',
			'Team Player',
			'Time Management',
			'Adaptability',
			'Documentation'
		]
	};

	let certifications = [
		{
			name: 'Eagle Scout',
			issuer: 'Scouting BSA - Troop 37',
			date: '2025'
		},
		{
			name: 'Exceptional Leadership',
			issuer: 'Suit Up - Battle of the Boroughs',
			date: '2024'
		}
	];

	let projects = [
		{
			name: 'iCommunity - Custom Community Platform',
			description:
				'Developed a customizable web platform for gaming communities featuring user role management, discussion forums, and real-time chat. Built under the Intellisoft Reborn brand using modern web technologies.'
		},
		{
			name: 'Intellisoft Labs - Web Design Business',
			description:
				'Founded and operate a freelance web design studio building websites and tools for local businesses and organizations. SvelteKit, Tailwind CSS, and custom CMS integrations.'
		}
	];
</script>

<svelte:head>
	<title>{personalInfo.name} – Resume</title>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:opsz,wght@9..40,400;9..40,500;9..40,600&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div
	class="min-h-screen bg-slate-100 p-4 [-webkit-print-color-adjust:exact] [print-color-adjust:exact]"
>
	<div
		class="
		mx-auto grid max-w-[960px] grid-cols-[240px_1fr] grid-rows-[auto_1fr] overflow-hidden
		rounded-xl bg-white shadow-lg
		print:max-w-none print:rounded-none print:shadow-none
	"
	>
		<!-- HEADER — spans both columns -->
		<header
			class="col-span-2 flex items-end justify-between gap-6 bg-[#0f1f3d] px-8 pt-7 pb-6 text-white print:px-6 print:pt-5 print:pb-4"
		>
			<div>
				<h1 class="font-display mb-1.5 text-[2.4rem] leading-none tracking-tight">
					{personalInfo.name}
				</h1>
				<p class="text-[0.72rem] tracking-[0.15em] uppercase opacity-60">{personalInfo.title}</p>
			</div>
			<div class="text-right text-[0.75rem] leading-[1.85] opacity-80">
				<span>{personalInfo.email}</span>
				<span class="mx-1 opacity-40">·</span>
				<span>{personalInfo.phone}</span>
				<span class="mx-1 opacity-40">·</span>
				<span>{personalInfo.location}</span>
				<br />
				<a
					href={personalInfo.linkedin}
					target="_blank"
					rel="noopener noreferrer"
					class="text-blue-300 no-underline">linkedin.com/in/quezada-nl</a
				>
				<span class="mx-1 opacity-40">·</span>
				<a
					href={personalInfo.github}
					target="_blank"
					rel="noopener noreferrer"
					class="text-blue-300 no-underline">github.com/hypnoticsiege</a
				>
				<span class="mx-1 opacity-40">·</span>
				<a
					href={personalInfo.website}
					target="_blank"
					rel="noopener noreferrer"
					class="text-blue-300 no-underline">quezada.nl</a
				>
			</div>
		</header>

		<!-- SIDEBAR -->
		<aside class="flex flex-col gap-6 bg-[#1a3260] px-5 py-6 text-white print:px-4 print:py-5">
			<!-- Skills -->
			<div>
				<h3
					class="font-display mb-2.5 border-b border-white/15 pb-1.5 text-[0.62rem] tracking-[0.2em] uppercase opacity-50"
				>
					Skills
				</h3>
				<p class="mb-1.5 text-[0.62rem] tracking-[0.1em] uppercase opacity-50">Technical</p>
				<div class="mb-3 flex flex-wrap gap-1.5">
					{#each skills.technical as skill}
						<span
							class="rounded border border-white/20 bg-white/10 px-2 py-0.5 text-[0.68rem] leading-relaxed"
							>{skill}</span
						>
					{/each}
				</div>
				<p class="mb-1.5 text-[0.62rem] tracking-[0.1em] uppercase opacity-50">Professional</p>
				<div class="flex flex-wrap gap-1.5">
					{#each skills.professional as skill}
						<span
							class="rounded border border-white/20 bg-white/10 px-2 py-0.5 text-[0.68rem] leading-relaxed"
							>{skill}</span
						>
					{/each}
				</div>
			</div>

			<!-- Certifications -->
			<div>
				<h3
					class="font-display mb-2.5 border-b border-white/15 pb-1.5 text-[0.62rem] tracking-[0.2em] uppercase opacity-50"
				>
					Certifications
				</h3>
				{#each certifications as cert}
					<div class="mb-2 flex items-start justify-between gap-2">
						<div>
							<p class="mb-0.5 text-[0.8rem] leading-snug font-medium">{cert.name}</p>
							<p class="text-[0.68rem] opacity-65">{cert.issuer}</p>
						</div>
						<span class="pt-0.5 text-[0.68rem] whitespace-nowrap opacity-50">{cert.date}</span>
					</div>
				{/each}
			</div>

			<!-- Education -->
			<div>
				<h3
					class="font-display mb-2.5 border-b border-white/15 pb-1.5 text-[0.62rem] tracking-[0.2em] uppercase opacity-50"
				>
					Education
				</h3>
				{#each education as edu, i}
					<div class={i < education.length - 1 ? 'mb-4' : ''}>
						<p class="mb-0.5 text-[0.8rem] leading-snug font-medium">{edu.degree}</p>
						<p class="text-[0.7rem] opacity-70">{edu.institution}</p>
						<p class="text-[0.66rem] opacity-50">{edu.period}</p>
						{#if edu.details}
							<p class="mt-0.5 text-[0.66rem] italic opacity-60">{edu.details}</p>
						{/if}
					</div>
				{/each}
			</div>
		</aside>

		<!-- MAIN -->
		<main class="flex flex-col gap-5 px-7 py-6 text-slate-800 print:px-6 print:py-5">
			<!-- Summary -->
			<section>
				<p class="border-l-[3px] border-blue-600 pl-3.5 text-[0.8rem] leading-[1.7] text-slate-500">
					{summary}
				</p>
			</section>

			<!-- Experience -->
			<section>
				<h2 class="font-display mb-3 border-b border-[#0f1f3d] pb-1 text-[1rem] text-[#0f1f3d]">
					Professional Experience
				</h2>
				{#each experience as job, i}
					<div class={i < experience.length - 1 ? 'mb-4' : ''}>
						<div class="flex items-center justify-between gap-2">
							<span class="text-[0.84rem] font-semibold text-slate-800">{job.title}</span>
							<span
								class="rounded bg-blue-600 px-2 py-0.5 text-[0.68rem] font-medium whitespace-nowrap text-white"
								>{job.period}</span
							>
						</div>
						<p class="mt-0.5 mb-1.5 text-[0.73rem] text-slate-500">
							{job.company} · {job.location}
						</p>
						{#if job.bullets?.length}
							<ul class="list-disc space-y-1 pl-4">
								{#each job.bullets as bullet}
									<li class="text-[0.76rem] leading-[1.55] text-slate-700">{bullet}</li>
								{/each}
							</ul>
						{/if}
					</div>
				{/each}
			</section>

			<!-- Projects -->
			{#if projects.length > 0}
				<section>
					<h2 class="font-display mb-3 border-b border-[#0f1f3d] pb-1 text-[1rem] text-[#0f1f3d]">
						Projects
					</h2>
					{#each projects as project, i}
						<div class={i < projects.length - 1 ? 'mb-3' : ''}>
							<p class="mb-0.5 text-[0.82rem] font-semibold text-[#1a3260]">{project.name}</p>
							{#if project.description}
								<p class="text-[0.76rem] leading-[1.55] text-slate-500">{project.description}</p>
							{/if}
						</div>
					{/each}
				</section>
			{/if}
		</main>
	</div>
</div>

<style>
	:global(body) {
		font-family: 'DM Sans', sans-serif;
	}
	:global(.font-display) {
		font-family: 'DM Serif Display', serif;
	}

	@media print {
		@page {
			size: 8.5in 11in;
			margin: 0.3in;
		}
		:global(body) {
			background: white !important;
			padding: 0 !important;
		}
	}
</style>
