<script lang="ts">
	import { onMount } from 'svelte';

	// Icons
	const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
	const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
	const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
	const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
	const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>`;
	const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
	const Linkedin = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
	const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 18"/></svg>`;

	let faqs = [
		{ question: "What is SCA certification and why does it matter?", open: false },
		{ question: "Do I need prior coffee experience to enroll?", open: false },
		{ question: "How long does it take to complete a certification course?", open: false },
		{ question: "Will I be ready to compete after completing the courses?", open: false },
		{ question: "What equipment do I need for the training?", open: false }
	];

	function toggleFaq(index: number) {
		faqs = faqs.map((faq, i) => {
			if (i === index) return { ...faq, open: !faq.open };
			return faq;
		});
	}
</script>

<div class="min-h-screen flex flex-col font-sans text-gray-900 bg-[#FAFAFA]">
	<!-- Top Banner -->
	<div class="bg-black text-white text-[11px] font-medium py-3 text-center tracking-wide px-4">
		Early bird discount: Save 20% on Foundation courses starting this month. Limited spots available.
	</div>

	<!-- Navigation -->
	<nav class="flex items-center justify-between px-6 md:px-12 py-5 bg-[#FAFAFA]">
		<div class="flex items-center gap-2">
			<!-- Logo -->
			<div class="flex items-center gap-3">
				<div class="w-8 h-8 text-primary-600">
					<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
						<mask
							id="mask0_161_7365"
							style="mask-type:luminance"
							maskUnits="userSpaceOnUse"
							x="3"
							y="1"
							width="18"
							height="22"
						>
							<path d="M3 1H20.7794V22.3353H3V1Z" fill="white" />
						</mask>
						<g mask="url(#mask0_161_7365)">
							<path
								d="M14.1516 3.24638L12.4034 2.77795L10.9302 8.27606L9.60014 3.31233L7.85194 3.78076L9.28896 9.14369L5.70969 5.56443L4.42993 6.84419L8.35594 10.7702L3.46671 9.46017L2.99829 11.2083L8.34038 12.6397C8.27922 12.3759 8.24687 12.1011 8.24687 11.8187C8.24687 9.81953 9.86746 8.19894 11.8666 8.19894C13.8657 8.19894 15.4863 9.81953 15.4863 11.8187C15.4863 12.0993 15.4544 12.3724 15.394 12.6347L20.2489 13.9356L20.7173 12.1874L15.354 10.7503L20.2436 9.44012L19.7751 7.69196L14.412 9.12898L17.9913 5.54972L16.7115 4.26998L12.84 8.14156L14.1516 3.24638Z"
								fill="currentColor"
							/>
							<path
								d="M15.3888 12.655C15.2389 13.2887 14.9225 13.8579 14.4883 14.314L18.0056 17.8313L19.2853 16.5515L15.3888 12.655Z"
								fill="currentColor"
							/>
							<path
								d="M14.4529 14.3508C14.0135 14.7996 13.4582 15.1345 12.8354 15.3071L14.1153 20.0836L15.8635 19.6151L14.4529 14.3508Z"
								fill="currentColor"
							/>
							<path
								d="M12.7701 15.3246C12.4812 15.3989 12.1784 15.4384 11.8663 15.4384C11.5319 15.4384 11.2082 15.393 10.9008 15.3082L9.61981 20.089L11.368 20.5574L12.7701 15.3246Z"
								fill="currentColor"
							/>
							<path
								d="M10.839 15.2905C10.2258 15.1093 9.68038 14.7702 9.24994 14.3201L5.72406 17.8459L7.00382 19.1257L10.839 15.2905Z"
								fill="currentColor"
							/>
							<path
								d="M9.22084 14.2889C8.79778 13.836 8.48962 13.2743 8.34294 12.6505L3.47211 13.9556L3.94053 15.7038L9.22084 14.2889Z"
								fill="currentColor"
							/>
						</g>
					</svg>
				</div>
				<span class="text-xl font-bold tracking-tight">Coffee Academy</span>
			</div>
		</div>
		<div class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
			<a href="#" class="hover:text-black transition-colors">Courses</a>
			<a href="#" class="hover:text-black transition-colors">About</a>
			<a href="#" class="hover:text-black transition-colors">FAQ</a>
			<a href="#" class="hover:text-black transition-colors">Contact</a>
			<a href="#" class="bg-black text-white px-5 py-2 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors">Enroll now</a>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="flex flex-col items-center pt-16 pb-20 px-4 text-center">
		<h1 class="text-4xl md:text-[56px] leading-[1.1] font-medium tracking-tight max-w-3xl mb-6">
			Master the art of coffee.<br>Earn your certification.
		</h1>
		<p class="text-gray-500 text-[15px] max-w-xl mb-8 leading-relaxed">
			Professional barista certification through SCA-aligned courses. From home brewing fundamentals to competition-level technique mastery. Start your coffee journey today.
		</p>
		<button class="bg-black text-white px-6 py-3 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors mb-20">
			Explore courses
		</button>

		<!-- Horizontal Scroll Images -->
		<div class="w-full max-w-[1400px] overflow-hidden relative mt-12">
			<div class="flex gap-6 justify-center items-center h-[320px]">
				<!-- Image 1 -->
				<div class="w-[200px] h-[260px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-2deg] translate-y-4">
					<img src="/generated/image-professional-barista-practicing-latte-ar-1765945095853-0.webp" alt="Barista practicing latte art" class="w-full h-full object-cover" />
				</div>
				<!-- Image 2 -->
				<div class="w-[260px] h-[180px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[1deg] -translate-y-2">
					<img src="/generated/image-coffee-beans-being-poured-into-grinder-h-1765945112938-5.webp" alt="Coffee beans" class="w-full h-full object-cover" />
				</div>
				<!-- Image 3 -->
				<div class="w-[220px] h-[220px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-1deg] translate-y-2">
					<img src="/generated/image-barista-student-learning-espresso-extrac-1765945103594-2.webp" alt="Barista training" class="w-full h-full object-cover" />
				</div>
				<!-- Image 4 -->
				<div class="w-[200px] h-[200px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[2deg] -translate-y-4">
					<img src="/generated/image-hands-holding-a-perfectly-crafted-cappuc-1765945100640-1.webp" alt="Latte art" class="w-full h-full object-cover" />
				</div>
				<!-- Image 5 -->
				<div class="w-[180px] h-[260px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-2deg] translate-y-6">
					<img src="/generated/image-barista-operating-professional-espresso--1765945109785-4.webp" alt="Espresso machine" class="w-full h-full object-cover" />
				</div>
				<!-- Image 6 -->
				<div class="w-[200px] h-[160px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[1deg] -translate-y-2">
					<img src="/generated/image-coffee-cupping-session-with-multiple-cup-1765945106713-3.webp" alt="Coffee cupping" class="w-full h-full object-cover" />
				</div>
			</div>
		</div>
	</section>

	<!-- Curriculum Showcase -->
	<section class="py-24 px-6 md:px-12 flex justify-center">
		<div class="bg-white rounded-[32px] p-12 md:p-20 flex flex-col md:flex-row items-center gap-16 max-w-[1200px] w-full shadow-sm">
			<!-- Curriculum Visual -->
			<div class="relative w-[320px] h-[420px] bg-gradient-to-br from-primary-50 to-primary-100 rounded-[32px] p-8 shadow-xl flex-shrink-0">
				<div class="text-sm font-bold text-primary-900 mb-6">SCA-Aligned Curriculum</div>
				<div class="space-y-4">
					<div class="bg-white rounded-xl p-4 shadow-sm">
						<div class="flex items-center gap-3 mb-2">
							<div class="w-8 h-8 bg-primary-500 rounded-lg flex items-center justify-center text-white text-xs font-bold">1</div>
							<div class="text-sm font-medium">Coffee Fundamentals</div>
						</div>
						<div class="text-xs text-gray-500 ml-11">Origin, processing, roasting basics</div>
					</div>
					<div class="bg-white rounded-xl p-4 shadow-sm">
						<div class="flex items-center gap-3 mb-2">
							<div class="w-8 h-8 bg-primary-500 rounded-lg flex items-center justify-center text-white text-xs font-bold">2</div>
							<div class="text-sm font-medium">Espresso Mastery</div>
						</div>
						<div class="text-xs text-gray-500 ml-11">Extraction, dialing in, consistency</div>
					</div>
					<div class="bg-white rounded-xl p-4 shadow-sm">
						<div class="flex items-center gap-3 mb-2">
							<div class="w-8 h-8 bg-primary-500 rounded-lg flex items-center justify-center text-white text-xs font-bold">3</div>
							<div class="text-sm font-medium">Milk Techniques</div>
						</div>
						<div class="text-xs text-gray-500 ml-11">Steaming, texturing, latte art</div>
					</div>
					<div class="bg-white rounded-xl p-4 shadow-sm">
						<div class="flex items-center gap-3 mb-2">
							<div class="w-8 h-8 bg-primary-500 rounded-lg flex items-center justify-center text-white text-xs font-bold">4</div>
							<div class="text-sm font-medium">Brewing Methods</div>
						</div>
						<div class="text-xs text-gray-500 ml-11">Pour over, immersion, cold brew</div>
					</div>
				</div>
			</div>

			<!-- Content -->
			<div class="flex-1 max-w-lg">
				<h2 class="text-3xl font-medium mb-6 leading-tight">
					Structured learning paths designed for real-world success.
				</h2>
				<p class="text-gray-500 text-[15px] leading-relaxed mb-6">
					Our curriculum follows Specialty Coffee Association standards, ensuring you learn the techniques and knowledge that matter most in today's coffee industry. From foundational skills to advanced competition techniques, every module builds your expertise systematically.
				</p>
				<div class="flex items-center gap-6 mt-8">
					<div class="text-center">
						<div class="text-3xl font-bold text-primary-600 mb-1">500+</div>
						<div class="text-xs text-gray-500">Certified Students</div>
					</div>
					<div class="w-px h-12 bg-gray-200"></div>
					<div class="text-center">
						<div class="text-3xl font-bold text-primary-600 mb-1">95%</div>
						<div class="text-xs text-gray-500">Pass Rate</div>
					</div>
					<div class="w-px h-12 bg-gray-200"></div>
					<div class="text-center">
						<div class="text-3xl font-bold text-primary-600 mb-1">12+</div>
						<div class="text-xs text-gray-500">Years Experience</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Lifestyle Grid -->
	<section class="py-20 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="flex flex-col md:flex-row justify-between items-start mb-16 gap-10">
			<h2 class="text-4xl md:text-5xl font-medium tracking-tight max-w-md leading-[1.1]">
				Transform your passion into professional expertise.
			</h2>
			<p class="text-gray-500 text-[15px] max-w-md leading-relaxed">
				Whether you're starting your coffee journey or aiming for competition success, our training programs provide the skills, confidence, and certification you need to thrive in the specialty coffee industry.
			</p>
		</div>

		<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
			<!-- Card 1 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-confident-barista-behind-espresso-bar-we-1765945115980-6.webp" alt="Professional barista" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Launch your career.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Gain the certification and skills that coffee shops actively seek in their baristas.</p>
				</div>
			</div>
			<!-- Card 2 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-group-of-diverse-students-in-coffee-trai-1765945119094-7.webp" alt="Coffee training class" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Learn from the best.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Train with experienced professionals who are passionate about sharing their expertise.</p>
				</div>
			</div>
			<!-- Card 3 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-barista-competition-participant-performi-1765945122298-8.webp" alt="Barista competition" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Compete with confidence.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Prepare for regional and international coffee competitions with advanced training.</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Testimonial -->
	<section class="py-24 px-6 text-center bg-[#F5F5F3]">
		<div class="max-w-3xl mx-auto">
			<blockquote class="text-2xl md:text-3xl font-medium leading-tight mb-10">
				"This academy transformed my coffee knowledge from casual enthusiasm to professional expertise. The hands-on training and SCA-aligned curriculum gave me the confidence to not only work as a barista but to compete at a national level."
			</blockquote>
			<div class="flex flex-col items-center gap-3">
				<img src="/generated/image-experienced-coffee-professional-teaching-1765945125467-9.webp" alt="Coffee professional" class="w-12 h-12 rounded-full object-cover" />
				<div class="text-sm">
					<div class="font-bold">Pim Rattanakorn</div>
					<div class="text-gray-500">2023 Thailand Barista Champion</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Process Steps -->
	<section class="py-20 px-6 md:px-12 max-w-[1400px] mx-auto w-full border-b border-gray-200">
		<div class="grid grid-cols-1 md:grid-cols-3 gap-12">
			<div>
				<h3 class="text-xl font-medium mb-2">Small class sizes.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Maximum 8 students per class ensures personalized attention and hands-on practice time.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">Professional equipment.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Train on industry-standard espresso machines, grinders, and brewing equipment.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">Completion guarantee.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">We support you until you pass your certification with confidence.</p>
			</div>
		</div>
	</section>

	<!-- How it works -->
	<section class="py-24 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="flex flex-col lg:flex-row gap-20">
			<!-- Sticky Title -->
			<div class="lg:w-1/3 lg:sticky lg:top-24 h-fit">
				<h2 class="text-4xl font-medium mb-6">Your learning journey.</h2>
				<p class="text-gray-500 text-[15px] leading-relaxed max-w-xs">
					From enrollment to certification, we guide you through every step. Our structured approach ensures you build skills progressively and gain the confidence to excel in your coffee career.
				</p>
			</div>

			<!-- Steps List -->
			<div class="lg:w-2/3 flex flex-col gap-8">
				<!-- Step 1 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">1</div>
						<h3 class="text-2xl font-medium mb-3">Choose your course level.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Select from Foundation, Intermediate, or Professional tracks based on your experience and goals. Each level builds comprehensive coffee knowledge.</p>
					</div>
					<div class="w-[240px] h-[420px] bg-gradient-to-br from-primary-50 to-white rounded-[24px] p-6 shadow-xl">
						<div class="space-y-3">
                            <div class="bg-white rounded-xl p-4 shadow-sm border-2 border-primary-400">
                                <div class="text-xs font-bold text-primary-700 mb-1">Foundation</div>
                                <div class="text-[10px] text-gray-500">Perfect for beginners</div>
                            </div>
                            <div class="bg-white rounded-xl p-4 shadow-sm">
                                <div class="text-xs font-bold text-gray-700 mb-1">Intermediate</div>
                                <div class="text-[10px] text-gray-500">For experienced baristas</div>
                            </div>
                            <div class="bg-white rounded-xl p-4 shadow-sm">
                                <div class="text-xs font-bold text-gray-700 mb-1">Professional</div>
                                <div class="text-[10px] text-gray-500">Competition ready</div>
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 2 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">2</div>
						<h3 class="text-2xl font-medium mb-3">Attend hands-on classes.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Learn through practical experience with professional equipment. Small class sizes ensure personalized instruction and plenty of practice time.</p>
					</div>
					<div class="w-[240px] h-[420px] bg-gray-900 rounded-[24px] p-6 shadow-xl text-white">
                        <div class="text-center mb-6">
                            <div class="text-sm font-bold mb-2">Week 1-4</div>
                            <div class="text-[10px] text-gray-400">Intensive Training</div>
                        </div>
                        <div class="space-y-3">
                            <div class="bg-gray-800 rounded-lg p-3">
                                <div class="text-xs font-medium mb-1">Espresso Basics</div>
                                <div class="h-1 bg-primary-500 rounded w-full"></div>
                            </div>
                            <div class="bg-gray-800 rounded-lg p-3">
                                <div class="text-xs font-medium mb-1">Milk Steaming</div>
                                <div class="h-1 bg-primary-500 rounded w-3/4"></div>
                            </div>
                            <div class="bg-gray-800 rounded-lg p-3">
                                <div class="text-xs font-medium mb-1">Latte Art</div>
                                <div class="h-1 bg-gray-700 rounded w-1/2"></div>
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 3 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">3</div>
						<h3 class="text-2xl font-medium mb-3">Practice and refine skills.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Get feedback from experienced instructors as you perfect your technique. Repeat modules until you're confident and consistent.</p>
					</div>
					<div class="w-[240px] h-[420px] bg-white rounded-[24px] p-6 shadow-xl border border-gray-200">
                        <div class="text-center mb-6">
                            <div class="text-sm font-bold mb-2">Practice Sessions</div>
                            <div class="text-[10px] text-gray-500">Unlimited until mastery</div>
                        </div>
                        <div class="space-y-4">
                            <div class="border border-gray-200 rounded-lg p-3">
                                <div class="flex justify-between items-center mb-2">
                                    <div class="text-xs font-medium">Extraction</div>
                                    <div class="text-[10px] text-green-600 font-bold">✓ Mastered</div>
                                </div>
                                <div class="text-[10px] text-gray-400">45 practice shots</div>
                            </div>
                            <div class="border-2 border-primary-300 rounded-lg p-3 bg-primary-50">
                                <div class="flex justify-between items-center mb-2">
                                    <div class="text-xs font-medium">Latte Art</div>
                                    <div class="text-[10px] text-primary-600 font-bold">In Progress</div>
                                </div>
                                <div class="text-[10px] text-gray-500">28 practice pours</div>
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 4 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">4</div>
						<h3 class="text-2xl font-medium mb-3">Pass your certification exam.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Demonstrate your skills in a practical assessment. Our completion guarantee means we support you until you succeed.</p>
					</div>
					<div class="w-[240px] h-[420px] bg-gradient-to-br from-green-50 to-white rounded-[24px] p-6 shadow-xl border-2 border-green-200">
                        <div class="text-center mb-6">
                            <div class="w-16 h-16 bg-green-500 rounded-full flex items-center justify-center mx-auto mb-3">
                                <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                                </svg>
                            </div>
                            <div class="text-sm font-bold mb-1">Certification Exam</div>
                            <div class="text-[10px] text-gray-500">Practical Assessment</div>
                        </div>
                        <div class="space-y-2 text-left">
                            <div class="text-[10px] text-gray-600 flex items-center gap-2">
                                <span class="text-green-500">✓</span> Espresso extraction
                            </div>
                            <div class="text-[10px] text-gray-600 flex items-center gap-2">
                                <span class="text-green-500">✓</span> Milk texturing
                            </div>
                            <div class="text-[10px] text-gray-600 flex items-center gap-2">
                                <span class="text-green-500">✓</span> Drink preparation
                            </div>
                            <div class="text-[10px] text-gray-600 flex items-center gap-2">
                                <span class="text-green-500">✓</span> Theory knowledge
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 5 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">5</div>
						<h3 class="text-2xl font-medium mb-3">Launch your coffee career.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Join our alumni network and access ongoing support. Advance to higher levels or compete professionally with your new skills.</p>
					</div>
					<div class="w-[240px] h-[420px] bg-gradient-to-br from-primary-500 to-primary-700 rounded-[24px] p-6 shadow-xl text-white">
                        <div class="text-center mb-6">
                            <div class="text-sm font-bold mb-2">SCA Certified</div>
                            <div class="text-[10px] text-primary-100">Barista Foundation Level</div>
                        </div>
                        <div class="bg-white/10 backdrop-blur rounded-xl p-4 mb-4">
                            <div class="text-xs font-medium mb-2">Next Steps</div>
                            <div class="space-y-2">
                                <div class="text-[10px] text-primary-100">→ Intermediate Course</div>
                                <div class="text-[10px] text-primary-100">→ Competition Training</div>
                                <div class="text-[10px] text-primary-100">→ Alumni Workshops</div>
                            </div>
                        </div>
                        <div class="text-[10px] text-primary-100 text-center">
                            Join 500+ certified baristas
                        </div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Dark Cards Section -->
	<section class="py-10 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
			<!-- Left Card -->
			<div class="bg-[#111] rounded-[32px] p-10 md:p-12 text-white min-h-[400px] flex flex-col relative overflow-hidden">
				<div class="relative z-10">
					<div class="text-xs text-gray-400 mb-2">SCA-Aligned Standards</div>
					<h3 class="text-2xl font-medium max-w-xs">Training recognized by the global coffee industry.</h3>
				</div>
				<!-- Coffee beans pattern -->
				<div class="absolute bottom-0 right-0 w-full h-64 opacity-10">
                    <svg viewBox="0 0 200 100" class="w-full h-full">
                        {#each Array(50) as _, i}
                            <ellipse cx={Math.random() * 200} cy={Math.random() * 100} rx="3" ry="4" fill="white" transform={`rotate(${Math.random() * 360} ${Math.random() * 200} ${Math.random() * 100})`} />
                        {/each}
                    </svg>
				</div>
			</div>
			<!-- Right Card -->
			<div class="bg-[#111] rounded-[32px] p-10 md:p-12 text-white min-h-[400px] flex flex-col relative overflow-hidden">
				<div class="relative z-10">
					<div class="text-xs text-gray-400 mb-2">Expert Instructors</div>
					<h3 class="text-2xl font-medium max-w-xs">Learn from competition winners and industry veterans.</h3>
				</div>
				<!-- Trophy/Award icons -->
				<div class="absolute bottom-8 right-8 flex gap-4 opacity-20">
					<div class="text-6xl">🏆</div>
					<div class="text-6xl">⭐</div>
					<div class="text-6xl">🥇</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Pricing Section -->
	<section class="py-24 px-6 md:px-12 max-w-[1400px] mx-auto w-full text-center">
		<h2 class="text-3xl md:text-4xl font-medium mb-4">Professional training at every level.</h2>
		<p class="text-gray-500 text-sm max-w-lg mx-auto mb-16">
			From beginner to competition-ready, our courses provide the skills and certification you need to succeed in the specialty coffee industry.
		</p>

		<div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl mx-auto">
			<!-- Foundation Plan -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm">
				<div class="w-10 h-10 bg-primary-100 rounded-lg mb-6 flex items-center justify-center">
					<div class="w-5 h-5 text-primary-600">
						<svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2L2 7v10c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V7l-10-5z"/></svg>
					</div>
				</div>
				<h3 class="text-xl font-bold mb-1">Foundation</h3>
				<p class="text-xs text-gray-500 mb-6">Perfect for beginners and home brewers.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">฿12,900</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">4-week intensive course</div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						Coffee fundamentals and origin knowledge
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						Espresso extraction and milk techniques
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						SCA Foundation certification exam included
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						Completion guarantee with unlimited practice
					</li>
				</ul>

				<button class="w-full bg-black text-white py-3 rounded-lg text-xs font-bold hover:bg-gray-800 transition-colors">Enroll now</button>
			</div>

			<!-- Professional Plan -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm border-2 border-primary-200 relative overflow-hidden">
                <div class="absolute top-0 right-0 bg-primary-500 text-white text-[10px] font-bold px-3 py-1 rounded-bl-xl">MOST POPULAR</div>
				<div class="w-10 h-10 bg-primary-500 rounded-lg mb-6 flex items-center justify-center">
					<div class="w-5 h-5 text-white">
						<svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
					</div>
				</div>
				<h3 class="text-xl font-bold mb-1">Professional</h3>
				<p class="text-xs text-gray-500 mb-6">Competition preparation and mastery.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">฿28,900</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">8-week advanced program</div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						Advanced brewing methods and sensory training
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						Competition techniques and performance coaching
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						SCA Professional certification exam included
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-500 shrink-0">{@html Check}</span>
						One-on-one mentorship with competition winners
					</li>
				</ul>

				<button class="w-full bg-black text-white py-3 rounded-lg text-xs font-bold hover:bg-gray-800 transition-colors">Enroll now</button>
			</div>
		</div>
	</section>

	<!-- FAQ Section -->
	<section class="py-20 px-6 md:px-12 max-w-3xl mx-auto w-full">
		<h2 class="text-3xl font-medium text-center mb-16">Your questions answered.</h2>
		<div class="space-y-4">
			{#each faqs as faq, i}
				<button 
					class="w-full flex items-center justify-between p-4 text-left hover:bg-gray-100 rounded-lg transition-colors group"
					onclick={() => toggleFaq(i)}
				>
					<span class="text-sm font-medium text-gray-800">{faq.question}</span>
					<span class="text-gray-400 transition-transform duration-200 {faq.open ? 'rotate-45' : ''}">{@html Plus}</span>
				</button>
                {#if faq.open}
                    <div class="px-4 pb-4 text-xs text-gray-500 leading-relaxed">
                        {#if i === 0}
                            SCA (Specialty Coffee Association) certification is the global standard for coffee professionals. It demonstrates your skills meet international quality standards and is recognized by specialty coffee shops worldwide.
                        {:else if i === 1}
                            No prior experience is required for our Foundation course. We welcome complete beginners, home brewers, and anyone passionate about learning coffee. Our instructors adapt to your skill level.
                        {:else if i === 2}
                            Foundation courses run 4 weeks with classes 3 times per week. Professional courses are 8 weeks. We also offer intensive weekend formats for those with limited availability.
                        {:else if i === 3}
                            Our Professional course includes competition preparation and coaching. Many of our graduates have competed successfully in regional and national competitions, with some advancing to international events.
                        {:else if i === 4}
                            All equipment is provided during training. You'll work with professional espresso machines, grinders, and brewing tools. We'll recommend equipment if you want to practice at home.
                        {/if}
                    </div>
                {/if}
			{/each}
		</div>
		<div class="text-center mt-12">
			<button class="bg-white border border-gray-200 px-6 py-3 rounded text-xs font-medium hover:bg-gray-50 transition-colors">
				View all Frequently Asked Questions
			</button>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-[#F5F5F3] py-16 px-6 md:px-12 text-[11px] text-gray-500">
		<div class="max-w-[1400px] mx-auto">
			<div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-12 gap-8">
				<div class="flex items-center gap-3">
					<div class="w-8 h-8 text-primary-600">
						<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
							<mask
								id="mask0_161_7365"
								style="mask-type:luminance"
								maskUnits="userSpaceOnUse"
								x="3"
								y="1"
								width="18"
								height="22"
							>
								<path d="M3 1H20.7794V22.3353H3V1Z" fill="white" />
							</mask>
							<g mask="url(#mask0_161_7365)">
								<path
									d="M14.1516 3.24638L12.4034 2.77795L10.9302 8.27606L9.60014 3.31233L7.85194 3.78076L9.28896 9.14369L5.70969 5.56443L4.42993 6.84419L8.35594 10.7702L3.46671 9.46017L2.99829 11.2083L8.34038 12.6397C8.27922 12.3759 8.24687 12.1011 8.24687 11.8187C8.24687 9.81953 9.86746 8.19894 11.8666 8.19894C13.8657 8.19894 15.4863 9.81953 15.4863 11.8187C15.4863 12.0993 15.4544 12.3724 15.394 12.6347L20.2489 13.9356L20.7173 12.1874L15.354 10.7503L20.2436 9.44012L19.7751 7.69196L14.412 9.12898L17.9913 5.54972L16.7115 4.26998L12.84 8.14156L14.1516 3.24638Z"
									fill="currentColor"
								/>
								<path
									d="M15.3888 12.655C15.2389 13.2887 14.9225 13.8579 14.4883 14.314L18.0056 17.8313L19.2853 16.5515L15.3888 12.655Z"
									fill="currentColor"
								/>
								<path
									d="M14.4529 14.3508C14.0135 14.7996 13.4582 15.1345 12.8354 15.3071L14.1153 20.0836L15.8635 19.6151L14.4529 14.3508Z"
									fill="currentColor"
								/>
								<path
									d="M12.7701 15.3246C12.4812 15.3989 12.1784 15.4384 11.8663 15.4384C11.5319 15.4384 11.2082 15.393 10.9008 15.3082L9.61981 20.089L11.368 20.5574L12.7701 15.3246Z"
									fill="currentColor"
								/>
								<path
									d="M10.839 15.2905C10.2258 15.1093 9.68038 14.7702 9.24994 14.3201L5.72406 17.8459L7.00382 19.1257L10.839 15.2905Z"
									fill="currentColor"
								/>
								<path
									d="M9.22084 14.2889C8.79778 13.836 8.48962 13.2743 8.34294 12.6505L3.47211 13.9556L3.94053 15.7038L9.22084 14.2889Z"
									fill="currentColor"
								/>
							</g>
						</svg>
					</div>
					<span class="text-lg font-bold tracking-tight text-black">Coffee Academy</span>
				</div>
				<div class="flex flex-wrap gap-6 font-medium text-gray-600">
					<a href="#" class="hover:text-black">Courses</a>
					<a href="#" class="hover:text-black">About</a>
					<a href="#" class="hover:text-black">FAQ</a>
					<a href="#" class="hover:text-black">Contact</a>
					<a href="#" class="hover:text-black">Terms & Conditions</a>
				</div>
				<div class="flex gap-4">
					<a href="#" class="text-black hover:text-gray-600">{@html Instagram}</a>
					<a href="#" class="text-black hover:text-gray-600">{@html Linkedin}</a>
				</div>
			</div>
			
			<div class="space-y-4 leading-relaxed opacity-60">
				<p>Coffee Academy is an independent training institution providing SCA-aligned barista certification courses. Our programs are designed to meet Specialty Coffee Association standards and prepare students for professional careers in the coffee industry.</p>
				<p>Course completion does not guarantee employment, but our certified graduates have a strong track record of success in specialty coffee shops and competitions. Individual results may vary based on dedication and practice.</p>
				<p>All course fees include materials, equipment use during training, and certification exam fees. Additional practice sessions and retakes are available at no extra cost under our completion guarantee.</p>
			</div>
		</div>
	</footer>
</div>

<style>
    /* Hide scrollbar for horizontal scroll */
    .overflow-hidden::-webkit-scrollbar {
        display: none;
    }
</style>

