<script>
	let personalInfo = {
		name: 'Luis Quezada',
		title: 'IT Student & Developer',
		email: 'luis@quezada.nl',
		phone: '(929) 595 6327',
		location: 'Staten Island, NY',
		linkedin: 'https://linkedin.com/in/quezada-nl',
		github: 'https://github.com/hypnoticsiege',
		website: 'Https://quezada.nl'
	};

	let summary = `Dedicated IT student and developer with a passion for creating complex web applications and providing exceptional technical support. Skilled in various programming languages, with a strong foundation in problem-solving and customer service.`;

	let experience = [
		{
			title: 'Service Representative',
			company: 'Planet Fitness',
			location: 'Staten Island, NY',
			period: '2025 - Present',
			description:
				'Assisting members with their fitness goals and providing exceptional customer service.',
			bullets: [
				'Provided information about the gym and membership options promptly and courteously.',
				'Guided members on using our mobile app for account management and check-ins.',
				'Assisted members on troubleshooting our Wi-Fi & Bluetooth connectivity to equipment.'
			]
		},
		{
			title: 'Sales Associate',
			company: 'T.J. Maxx',
			location: 'Staten Island, NY',
			period: '2024 - 2025',
			description: 'Created custom websites and web tools for individuals and small businesses.',
			bullets: [
				'Multitasked effectively in a fast-paced retail environment, ensuring customer satisfaction.',
				'Collaborated with team members to achieve targets and enhance the customer experience.',
				'Maintained a thorough knowledge of store products to assist customers effectively.'
			]
		}
	];

	let education = [
		{
			degree: 'High School Diploma',
			institution: 'Lavelle Prepratory Charter School',
			location: 'Staten Island, NY',
			period: '2021 - 2025',
			details: 'AP English, Spanish, & Pre-Calculus'
		},
		{
			degree: 'Computer Technology (AAS)',
			institution: 'Community College of Staten Island',
			location: 'Staten Island, NY',
			period: '2025 - Present',
			details:
				'Studying various technical subjects including programming, networking, and database management.'
		}
	];

	let skills = {
		technical: [
			'HTML/CSS',
			'TypeScript',
			'Svelte',
			'TailwindCSS',
			'Node.js',
			'Git',
			'Linux',
			'Docker',
			'SQL'
		],
		professional: [
			'Customer Service',
			'Problem Solving',
			'Communication',
			'Teamwork',
			'Time Management',
			'Flexibility',
			'Work Ethic'
		]
	};

	let certifications = [
		{
			name: 'Eagle Scout',
			issuer: 'Scouting BSA - Troop 37',
			date: '2025'
		}
	];

	let projects = [
		{
			name: 'iCommunity – Custom Community Platform',
			period: 'Jan 2025 – Present',
			description:
				'Developed a customizable web platform for gaming communities with user roles, forums, and real-time chat features.'
		},
		{
			name: 'Restaurant/Food Truck Template',
			period: 'Sep 2025 – Nov 2025',
			description:
				'Created a ready-to-use template for small food businesses to showcase menus, locations, and online ordering links.'
		}
	];
</script>

<svelte:head>
	<title>{personalInfo.name} - Resume</title>
</svelte:head>

<div
	class="resume-container mx-auto max-w-5xl overflow-hidden rounded-lg bg-white shadow-lg print:max-w-none print:shadow-none"
>
	<!-- Header -->
	<header
		class="resume-header bg-gradient-to-r from-blue-600 to-blue-800 p-8 text-white print:bg-white print:p-4 print:text-black"
	>
		<div class="text-center md:text-left">
			<!-- Name -->
			<h1 class="mb-1 text-4xl font-extrabold tracking-tight print:text-2xl">
				{personalInfo.name}
			</h1>

			<!-- Title / Role -->
			<h2 class="mb-4 text-xl font-light opacity-90 print:mb-2 print:text-lg">
				{personalInfo.title}
			</h2>

			<!-- Contact Info -->
			<div
				class="flex flex-wrap justify-center gap-4 text-sm md:justify-start print:gap-2 print:text-xs print:text-black"
			>
				<span>{personalInfo.email}</span>
				<span class="hidden text-gray-300 md:inline">•</span>
				<span>{personalInfo.phone}</span>
				<span class="hidden text-gray-300 md:inline">•</span>
				<span>{personalInfo.location}</span>
				<span class="hidden text-gray-300 md:inline">•</span>
				<a
					href={personalInfo.linkedin}
					target="_blank"
					rel="noopener noreferrer"
					class="print:no-underline"
				>
					LinkedIn
				</a>
				<span class="hidden text-gray-300 md:inline">•</span>
				<a
					href={personalInfo.website}
					target="_blank"
					rel="noopener noreferrer"
					class="print:no-underline"
				>
					{personalInfo.website}
				</a>
			</div>
		</div>
	</header>

	<!-- Main -->
	<main class="p-8 text-gray-800 print:p-4 print:text-sm">
		<!-- Summary -->
		<section class="mb-8 print:mb-3">
			<p class="leading-relaxed print:leading-snug">{summary}</p>
		</section>

		<div class="grid grid-cols-1 gap-8 lg:grid-cols-3 print:grid-cols-2">
			<!-- Left Column: Experience + Projects (ATS-Friendly) -->
			<div class="space-y-6 lg:col-span-2 print:space-y-3">
				<!-- Professional Experience -->
				<section>
					<h2 class="section-title mb-2 text-xl font-bold print:mb-1">Professional Experience</h2>

					{#each experience as job}
						<div class="mb-4 print:mb-2">
							<div class="flex flex-col md:flex-row md:items-baseline md:justify-between">
								<h3 class="text-lg font-bold">{job.title}</h3>
								<span class="mt-1 font-semibold md:mt-0 print:text-black">{job.period}</span>
							</div>

							<p class="mt-1 text-sm font-medium print:text-sm">
								{job.company} - {job.location}
							</p>

							{#if job.bullets?.length}
								<ul class="mt-1 list-inside list-disc space-y-1 text-sm print:space-y-0.5">
									{#each job.bullets as bullet}
										<li>{bullet}</li>
									{/each}
								</ul>
							{/if}
						</div>
					{/each}
				</section>

				<!-- Projects -->
				{#if projects.length > 0}
					<section>
						<h2 class="section-title mb-2 text-xl font-bold print:mb-1">Projects</h2>

						{#each projects as project}
							<div class="mb-4 print:mb-2">
								<div class="flex flex-col md:flex-row md:items-baseline md:justify-between">
									<h3 class="text-md font-semibold print:text-sm">{project.name}</h3>
									<span class="mt-1 text-sm text-gray-600 md:mt-0 print:text-black"
										>{project.period}</span
									>
								</div>

								{#if project.description}
									<p class="mt-1 text-sm print:text-sm">{project.description}</p>
								{/if}

								{#if project.bullets?.length}
									<ul class="mt-1 list-inside list-disc space-y-1 text-sm print:space-y-0.5">
										{#each project.bullets as bullet}
											<li>{bullet}</li>
										{/each}
									</ul>
								{/if}
							</div>
						{/each}
					</section>
				{/if}
			</div>

			<!-- Right Column -->
			<div class="space-y-10 print:space-y-4">
				<!-- Skills -->
				<section>
					<h2 class="section-title mb-3 text-xl font-bold">Skills</h2>

					<div class="rounded-lg border border-gray-200 bg-white p-4 print:border-0 print:p-0">
						<h3 class="mb-2 text-sm font-semibold tracking-wide text-gray-600 uppercase">
							Technical
						</h3>
						<div class="mb-4 flex flex-wrap gap-2">
							{#each skills.technical as skill}
								<span
									class="rounded-md bg-gray-100 px-2.5 py-1 text-sm text-gray-800 print:bg-transparent print:px-1 print:text-xs"
								>
									{skill}
								</span>
							{/each}
						</div>

						<h3 class="mb-2 text-sm font-semibold tracking-wide text-gray-600 uppercase">
							Professional
						</h3>
						<div class="flex flex-wrap gap-2">
							{#each skills.professional as skill}
								<span
									class="rounded-md bg-gray-100 px-2.5 py-1 text-sm text-gray-800 print:bg-transparent print:px-1 print:text-xs"
								>
									{skill}
								</span>
							{/each}
						</div>
					</div>
				</section>

				<!-- Certifications -->
				<section>
					<h2 class="section-title mb-3 text-xl font-bold">Certifications</h2>

					<div class="rounded-lg border border-gray-200 bg-white p-4 print:border-0 print:p-0">
						<ul class="space-y-2">
							{#each certifications as cert}
								<li class="flex items-start justify-between gap-4">
									<div>
										<p class="font-semibold">{cert.name}</p>
										<p class="text-sm text-gray-600">{cert.issuer}</p>
									</div>
									<p class="text-sm text-gray-500">{cert.date}</p>
								</li>
							{/each}
						</ul>
					</div>
				</section>

				<!-- Education -->
				<section>
					<h2 class="section-title mb-3 text-xl font-bold">Education</h2>

					<div class="space-y-4">
						{#each education as edu}
							<div class="rounded-lg border border-gray-200 bg-white p-4 print:border-0 print:p-0">
								<h3 class="font-bold">{edu.degree}</h3>
								<p class="font-semibold text-gray-700">
									{edu.institution} · {edu.location}
								</p>
								<p class="text-sm text-gray-500">{edu.period}</p>

								{#if edu.details}
									<p class="mt-2 text-sm">{edu.details}</p>
								{/if}
							</div>
						{/each}
					</div>
				</section>
			</div>
		</div>
	</main>
</div>

<style>
	@media print {
		@page {
			size: 8.5in 11in;
			margin: 0.4in;
		}

		body {
			background: white;
			font-size: 10pt;
			line-height: 1.2;
		}

		/* Scale down the resume to fit perfectly on one page */
		.resume-container {
			transform: scale(0.9);
			transform-origin: top left;
			width: 111%;
			max-height: 100%;
			page-break-after: avoid;
		}

		h1,
		h2,
		h3 {
			margin: 0;
			padding: 0;
		}

		* {
			color: black !important;
			box-shadow: none !important;
			background: none !important;
		}

		.resume-header {
			border-bottom: 1px solid #000;
		}
	}
</style>
