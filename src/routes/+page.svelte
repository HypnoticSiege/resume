<script>
	let personalInfo = {
		name: 'Luis Quezada',
		title: 'IT Student & Developer',
		email: 'luis@example.com',
		phone: '(929) 595 6327',
		location: 'Staten Island, NY',
		linkedin: 'linkedin.com/in/quezada-nl',
		github: 'github.com/hypnoticsiege'
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
		},
		{
			title: 'Technical Support Agent',
			company: 'Snowside Hosting',
			location: 'Remote',
			period: '2021 - 2023',
			description:
				'Provided technical support for web hosting services, assisting clients with website setup, troubleshooting, and maintenance.',

			bullets: [
				'Delivered prompt and effective solutions to customer inquiries via chat and email.',
				'Diagnosed and resolved technical issues related to website hosting and domain management.',
				'Maintained high customer satisfaction ratings through attentive and personalized service.'
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
		professional: ['Leadership', 'Communication', 'Project Management', 'Problem Solving']
	};

	let certifications = [
		{
			name: 'Eagle Scout',
			issuer: 'Scouting BSA - Troop 37',
			date: '2025',
			skills: ['Leadership', 'Teamwork', 'Community Service']
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
			<h1 class="mb-1 text-4xl font-bold">{personalInfo.name}</h1>
			<h2 class="mb-3 text-xl font-light opacity-90">{personalInfo.title}</h2>
			<div
				class="flex flex-wrap justify-center gap-4 text-sm md:justify-start print:gap-2 print:text-xs"
			>
				<span>{personalInfo.email}</span>
				<span>•</span>
				<span>{personalInfo.phone}</span>
				<span>•</span>
				<span>{personalInfo.location}</span>
				<span>•</span>
				<span>{personalInfo.linkedin}</span>
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
			<!-- Left Column -->
			<div class="space-y-8 lg:col-span-2 print:space-y-1">
				<!-- Experience -->
				<section>
					<h2 class="section-title mb-4 text-xl font-bold">Professional Experience</h2>
					<div class="print:mb-4"></div>
					{#each experience as job}
						<div
							class="mb-6 border-l-4 border-blue-500 pl-4 print:mb-2 print:border-gray-200 print:pl-2"
						>
							<div class="flex items-start justify-between">
								<h3 class="text-lg font-bold">{job.title}</h3>
								<span class="font-semibold text-blue-600 print:text-black">{job.period}</span>
							</div>
							<p class="text-md font-semibold">{job.company} - {job.location}</p>
							<ul class="list-inside list-disc space-y-0 text-sm print:space-y-0.5">
								{#each job.bullets as bullet}
									<li>{bullet}</li>
								{/each}
							</ul>
						</div>
						<div class="print:mb-4"></div>
					{/each}
					<div class="print:mb-2"></div>
				</section>

				<!-- Certifications -->
				<section>
					<h2 class="section-title mb-2 text-xl font-bold">Certifications</h2>
					<div class="grid grid-cols-1 gap-4 print:gap-2">
						{#each certifications as cert}
							<div class="mb-4 print:mb-2">
								<h3 class="text-lg font-semibold print:text-base">{cert.name}</h3>
								<p class="font-semibold">
									{cert.issuer} - <span class="font-normal">{cert.date}</span>
								</p>
								<div class="mt-1 flex flex-wrap gap-2">
									{#each cert.skills as skill}
										<span class="rounded bg-gray-100 px-2 py-1 text-sm print:text-xs">{skill}</span>
									{/each}
								</div>
							</div>
						{/each}
					</div>
				</section>
			</div>

			<!-- Right Column -->
			<div class="space-y-8 print:space-y-2">
				<!-- Skills -->
				<h2 class="section-title mb-2 text-xl font-bold">Skills</h2>
				<section>
					<h3 class="text-md mb-2 font-semibold">Technical</h3>
					<div class="mb-3 flex flex-wrap gap-2">
						{#each skills.technical as skill}
							<span class="rounded bg-gray-100 px-2 py-1 text-sm print:text-xs">{skill}</span>
						{/each}
					</div>
					<div class="print:mb-2"></div>
					<h3 class="text-md mb-2 font-semibold">Professional</h3>
					<div class="flex flex-wrap gap-2">
						{#each skills.professional as skill}
							<span class="rounded bg-gray-100 px-2 py-1 text-sm print:text-xs">{skill}</span>
						{/each}
					</div>
					<div class="print:mb-4"></div>
				</section>

				<!-- Education -->
				<section>
					<h2 class="section-title mb-2 text-xl font-bold">Education</h2>
					{#each education as edu}
						<div class="mb-2">
							<h3 class="font-bold">{edu.degree}</h3>
							<p class="font-semibold">{edu.institution} - {edu.location}</p>
							<p class="text-sm">{edu.period}</p>
							<p>{edu.details}</p>
						</div>
						<div class="print:mb-4"></div>
					{/each}
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
