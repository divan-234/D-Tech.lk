<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Divan Rathnayaka | Web Developer Portfolio</title>
   <meta name="description" content="Portfolio of Divan Rathnayaka, a creative Web Developer specializing in modern web technologies.">
   
   <!-- Tailwind CSS -->
   <script src="https://cdn.tailwindcss.com"></script>
   
   <!-- Google Fonts -->
   <link rel="preconnect" href="https://fonts.googleapis.com">
   <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
   <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700&family=Space+Grotesk:wght@300;500;700&display=swap" rel="stylesheet">
   
   <!-- Font Awesome -->
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

   <!-- Tailwind Config -->
   <script>
       tailwind.config = {
           theme: {
               extend: {
                   fontFamily: {
                       sans: ['Outfit', 'sans-serif'],
                       display: ['Space Grotesk', 'sans-serif'],
                   },
                   colors: {
                       primary: '#0f172a', // Slate 900
                       secondary: '#3b82f6', // Blue 500
                       accent: '#06b6d4', // Cyan 500
                       surface: '#ffffff',
                   },
                   animation: {
                       'blob': 'blob 7s infinite',
                       'fade-in-up': 'fadeInUp 0.8s ease-out forwards',
                   },
                   keyframes: {
                       blob: {
                           '0%': { transform: 'translate(0px, 0px) scale(1)' },
                           '33%': { transform: 'translate(30px, -50px) scale(1.1)' },
                           '66%': { transform: 'translate(-20px, 20px) scale(0.9)' },
                           '100%': { transform: 'translate(0px, 0px) scale(1)' },
                       },
                       fadeInUp: {
                           '0%': { opacity: '0', transform: 'translateY(20px)' },
                           '100%': { opacity: '1', transform: 'translateY(0)' },
                       }
                   }
               }
           }
       }
   </script>

   <style>
       /* Custom Scrollbar */
       ::-webkit-scrollbar {
           width: 10px;
       }
       ::-webkit-scrollbar-track {
           background: #f1f1f1;
       }
       ::-webkit-scrollbar-thumb {
           background: #cbd5e1;
           border-radius: 5px;
       }
       ::-webkit-scrollbar-thumb:hover {
           background: #94a3b8;
       }

       /* Utilities */
       .glass-nav {
           background: rgba(255, 255, 255, 0.8);
           backdrop-filter: blur(12px);
           -webkit-backdrop-filter: blur(12px);
           border-bottom: 1px solid rgba(255, 255, 255, 0.3);
       }

       .text-gradient {
           background: linear-gradient(to right, #3b82f6, #06b6d4);
           -webkit-background-clip: text;
           -webkit-text-fill-color: transparent;
       }

       /* Animation Classes */
       .reveal {
           opacity: 0;
           transform: translateY(30px);
           transition: all 0.8s ease-out;
       }
       .reveal.active {
           opacity: 1;
           transform: translateY(0);
       }

       /* Skill Bar Animation */
       .skill-track {
           width: 100%;
           background-color: #e2e8f0;
           border-radius: 999px;
           overflow: hidden;
       }
       .skill-fill {
           height: 100%;
           width: 0;
           background: linear-gradient(90deg, #3b82f6, #06b6d4);
           border-radius: 999px;
           transition: width 1.5s cubic-bezier(0.22, 1, 0.36, 1);
       }
   </style>
</head>
<body class="bg-slate-50 text-slate-800 antialiased overflow-x-hidden">

   <!-- Navigation -->
   <nav id="navbar" class="fixed w-full z-50 transition-all duration-300 py-4">
       <div class="container mx-auto px-6 flex justify-between items-center">
           <a href="#" class="text-2xl font-display font-bold tracking-tighter text-slate-900 flex items-center gap-2">
               <span class="w-8 h-8 bg-gradient-to-br from-blue-500 to-cyan-400 rounded-lg flex items-center justify-center text-white text-sm">DR</span>
               Divan<span class="text-blue-600">.</span>
           </a>

           <!-- Desktop Menu -->
           <div class="hidden md:flex items-center space-x-8">
               <a href="#home" class="text-sm font-medium text-slate-600 hover:text-blue-600 transition-colors">Home</a>
               <a href="#about" class="text-sm font-medium text-slate-600 hover:text-blue-600 transition-colors">About</a>
               <a href="#skills" class="text-sm font-medium text-slate-600 hover:text-blue-600 transition-colors">Skills</a>
               <a href="#projects" class="text-sm font-medium text-slate-600 hover:text-blue-600 transition-colors">Projects</a>
               <a href="#contact" class="px-5 py-2.5 text-sm font-medium text-white bg-slate-900 rounded-full hover:bg-blue-600 transition-all shadow-lg hover:shadow-blue-500/30">Contact Me</a>
           </div>

           <!-- Mobile Menu Button -->
           <button id="mobile-menu-btn" class="md:hidden text-slate-800 focus:outline-none">
               <i class="fas fa-bars text-2xl"></i>
           </button>
       </div>

       <!-- Mobile Menu Dropdown -->
       <div id="mobile-menu" class="hidden md:hidden absolute top-full left-0 w-full bg-white shadow-xl border-t border-slate-100 py-4 px-6 flex flex-col space-y-4">
           <a href="#home" class="text-slate-600 hover:text-blue-600 font-medium">Home</a>
           <a href="#about" class="text-slate-600 hover:text-blue-600 font-medium">About</a>
           <a href="#skills" class="text-slate-600 hover:text-blue-600 font-medium">Skills</a>
           <a href="#projects" class="text-slate-600 hover:text-blue-600 font-medium">Projects</a>
           <a href="#contact" class="text-blue-600 font-bold">Contact Me</a>
       </div>
   </nav>

   <!-- Hero Section -->
   <section id="home" class="relative min-h-screen flex items-center pt-20 overflow-hidden">
       <!-- Background Blobs -->
       <div class="absolute top-0 -left-4 w-72 h-72 bg-purple-300 rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-blob"></div>
       <div class="absolute top-0 -right-4 w-72 h-72 bg-cyan-300 rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-blob animation-delay-2000"></div>
       <div class="absolute -bottom-8 left-20 w-72 h-72 bg-blue-300 rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-blob animation-delay-4000"></div>

       <div class="container mx-auto px-6 relative z-10 grid md:grid-cols-2 gap-12 items-center">
           <div class="order-2 md:order-1 space-y-6 reveal active">
               <div class="inline-block px-3 py-1 rounded-full bg-blue-50 border border-blue-100 text-blue-600 text-xs font-bold tracking-wide uppercase mb-2">
                   Available for hire
               </div>
               <h1 class="text-5xl md:text-7xl font-display font-bold leading-tight text-slate-900">
                   Hi, I'm <span class="text-gradient">Divan</span><br>
                   Rathnayaka
               </h1>
               <h2 class="text-2xl md:text-3xl text-slate-500 font-light">
                   Creative <span class="text-slate-800 font-medium border-b-2 border-cyan-400">Web Developer</span>
               </h2>
               <p class="text-lg text-slate-600 max-w-lg leading-relaxed">
                   I craft visually stunning and highly functional digital experiences. Let's build something amazing together.
               </p>
               <div class="flex flex-wrap gap-4 pt-4">
                   <a href="#projects" class="px-8 py-3.5 bg-slate-900 text-white rounded-full font-medium hover:bg-blue-600 transition-all shadow-lg hover:shadow-blue-500/40 hover:-translate-y-1">
                       View My Work
                   </a>
                   <a href="#contact" class="px-8 py-3.5 bg-white text-slate-900 border border-slate-200 rounded-full font-medium hover:border-blue-600 hover:text-blue-600 transition-all hover:-translate-y-1">
                       Let's Talk
                   </a>
               </div>
               
               <div class="flex items-center gap-6 pt-8 text-slate-400">
                   <a href="#" class="hover:text-slate-900 transition-colors text-xl"><i class="fab fa-github"></i></a>
                   <a href="#" class="hover:text-blue-600 transition-colors text-xl"><i class="fab fa-linkedin"></i></a>
                   <a href="#" class="hover:text-pink-600 transition-colors text-xl"><i class="fab fa-dribbble"></i></a>
                   <a href="#" class="hover:text-sky-500 transition-colors text-xl"><i class="fab fa-twitter"></i></a>
               </div>
           </div>

           <div class="order-1 md:order-2 flex justify-center reveal active delay-200">
               <div class="relative w-72 h-72 md:w-96 md:h-96">
                   <div class="absolute inset-0 bg-gradient-to-tr from-blue-500 to-cyan-400 rounded-full opacity-20 blur-2xl animate-pulse"></div>
                   <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" 
                        alt="Divan Rathnayaka" 
                        class="relative w-full h-full object-cover rounded-full border-4 border-white shadow-2xl z-10 grayscale hover:grayscale-0 transition-all duration-500">
                   
                   <!-- Floating Badge -->
                   <div class="absolute bottom-4 -right-4 bg-white p-4 rounded-2xl shadow-xl z-20 animate-bounce" style="animation-duration: 3s;">
                       <div class="flex items-center gap-3">
                           <div class="w-10 h-10 bg-green-100 rounded-full flex items-center justify-center text-green-600">
                               <i class="fas fa-code"></i>
                           </div>
                           <div>
                               <p class="text-xs text-slate-500 font-bold uppercase">Experience</p>
                               <p class="text-slate-900 font-bold">5+ Years</p>
                           </div>
                       </div>
                   </div>
               </div>
           </div>
       </div>
   </section>

   <!-- About Section -->
   <section id="about" class="py-24 bg-white">
       <div class="container mx-auto px-6">
           <div class="flex flex-col md:flex-row items-center gap-16">
               <div class="w-full md:w-1/2 reveal">
                   <div class="relative">
                       <div class="absolute -top-4 -left-4 w-24 h-24 bg-blue-100 rounded-full -z-10"></div>
                       <div class="absolute -bottom-4 -right-4 w-32 h-32 bg-cyan-100 rounded-full -z-10"></div>
                       <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" 
                            alt="Workspace" 
                            class="rounded-2xl shadow-2xl w-full object-cover h-[400px]">
                   </div>
               </div>
               <div class="w-full md:w-1/2 reveal">
                   <h3 class="text-blue-600 font-bold tracking-wider uppercase mb-2">About Me</h3>
                   <h2 class="text-4xl font-display font-bold text-slate-900 mb-6">Design-driven Developer based in Sri Lanka</h2>
                   <p class="text-slate-600 leading-relaxed mb-6 text-lg">
                       Hello! I'm Divan Rathnayaka. I bridge the gap between design and engineering. With a keen eye for aesthetics and a solid foundation in code, I build web applications that not only look great but perform flawlessly.
                   </p>
                   <p class="text-slate-600 leading-relaxed mb-8">
                       My journey began with a curiosity for how things work on the internet, which quickly turned into a passion for creating. I specialize in the JavaScript ecosystem, focusing on React and modern frontend architecture, but I'm comfortable diving into backend logic when needed.
                   </p>
                   
                   <div class="grid grid-cols-2 gap-6">
                       <div class="p-4 bg-slate-50 rounded-xl border border-slate-100 hover:border-blue-200 transition-colors">
                           <i class="fas fa-laptop-code text-2xl text-blue-600 mb-2"></i>
                           <h4 class="font-bold text-slate-900">Clean Code</h4>
                           <p class="text-sm text-slate-500">Maintainable & Scalable</p>
                       </div>
                       <div class="p-4 bg-slate-50 rounded-xl border border-slate-100 hover:border-blue-200 transition-colors">
                           <i class="fas fa-rocket text-2xl text-cyan-600 mb-2"></i>
                           <h4 class="font-bold text-slate-900">Performance</h4>
                           <p class="text-sm text-slate-500">Optimized for Speed</p>
                       </div>
                   </div>
               </div>
           </div>
       </div>
   </section>

   <!-- Skills Section -->
   <section id="skills" class="py-24 bg-slate-50">
       <div class="container mx-auto px-6">
           <div class="text-center max-w-2xl mx-auto mb-16 reveal">
               <h3 class="text-blue-600 font-bold tracking-wider uppercase mb-2">My Expertise</h3>
               <h2 class="text-4xl font-display font-bold text-slate-900 mb-4">Tools & Technologies</h2>
               <p class="text-slate-600">I constantly keep up with the latest trends to ensure your project uses the best tools available.</p>
           </div>

           <div class="grid md:grid-cols-2 gap-12 max-w-4xl mx-auto">
               <!-- Skill Item -->
               <div class="reveal">
                   <div class="flex justify-between mb-2">
                       <span class="font-bold text-slate-800 flex items-center gap-2">
                           <i class="fab fa-html5 text-orange-500"></i> HTML5 & CSS3
                       </span>
                       <span class="text-slate-500 font-mono">95%</span>
                   </div>
                   <div class="skill-track h-3">
                       <div class="skill-fill" data-width="95%"></div>
                   </div>
               </div>

               <!-- Skill Item -->
               <div class="reveal delay-100">
                   <div class="flex justify-between mb-2">
                       <span class="font-bold text-slate-800 flex items-center gap-2">
                           <i class="fab fa-js text-yellow-400"></i> JavaScript (ES6+)
                       </span>
                       <span class="text-slate-500 font-mono">90%</span>
                   </div>
                   <div class="skill-track h-3">
                       <div class="skill-fill" data-width="90%"></div>
                   </div>
               </div>

               <!-- Skill Item -->
               <div class="reveal delay-200">
                   <div class="flex justify-between mb-2">
                       <span class="font-bold text-slate-800 flex items-center gap-2">
                           <i class="fab fa-react text-blue-400"></i> React.js
                       </span>
                       <span class="text-slate-500 font-mono">85%</span>
                   </div>
                   <div class="skill-track h-3">
                       <div class="skill-fill" data-width="85%"></div>
                   </div>
               </div>

               <!-- Skill Item -->
               <div class="reveal delay-300">
                   <div class="flex justify-between mb-2">
                       <span class="font-bold text-slate-800 flex items-center gap-2">
                           <i class="fab fa-node text-green-600"></i> Node.js
                       </span>
                       <span class="text-slate-500 font-mono">75%</span>
                   </div>
                   <div class="skill-track h-3">
                       <div class="skill-fill" data-width="75%"></div>
                   </div>
               </div>

               <!-- Skill Item -->
               <div class="reveal delay-400">
                   <div class="flex justify-between mb-2">
                       <span class="font-bold text-slate-800 flex items-center gap-2">
                           <i class="fas fa-wind text-cyan-400"></i> Tailwind CSS
                       </span>
                       <span class="text-slate-500 font-mono">95%</span>
                   </div>
                   <div class="skill-track h-3">
                       <div class="skill-fill" data-width="95%"></div>
                   </div>
               </div>

               <!-- Skill Item -->
               <div class="reveal delay-500">
                   <div class="flex justify-between mb-2">
                       <span class="font-bold text-slate-800 flex items-center gap-2">
                           <i class="fab fa-git-alt text-red-500"></i> Git & GitHub
                       </span>
                       <span class="text-slate-500 font-mono">80%</span>
                   </div>
                   <div class="skill-track h-3">
                       <div class="skill-fill" data-width="80%"></div>
                   </div>
               </div>
           </div>
       </div>
   </section>

   <!-- Projects Section -->
   <section id="projects" class="py-24 bg-white">
       <div class="container mx-auto px-6">
           <div class="flex flex-col md:flex-row justify-between items-end mb-16 reveal">
               <div class="max-w-2xl">
                   <h3 class="text-blue-600 font-bold tracking-wider uppercase mb-2">Portfolio</h3>
                   <h2 class="text-4xl font-display font-bold text-slate-900">Featured Projects</h2>
               </div>
               <a href="#" class="hidden md:inline-flex items-center gap-2 text-slate-900 font-bold hover:text-blue-600 transition-colors mt-4 md:mt-0 group">
                   View Github <i class="fas fa-arrow-right transform group-hover:translate-x-1 transition-transform"></i>
               </a>
           </div>

           <div class="grid md:grid-cols-3 gap-8">
               <!-- Project Card 1 -->
               <div class="group bg-white rounded-2xl overflow-hidden shadow-lg border border-slate-100 hover:shadow-2xl transition-all duration-300 hover:-translate-y-2 reveal">
                   <div class="relative h-64 overflow-hidden">
                       <div class="absolute inset-0 bg-slate-900/20 group-hover:bg-slate-900/0 transition-colors z-10"></div>
                       <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Dashboard" class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700">
                       <div class="absolute top-4 right-4 z-20 bg-white/90 backdrop-blur px-3 py-1 rounded-full text-xs font-bold text-slate-900 shadow-sm">
                           React
                       </div>
                   </div>
                   <div class="p-8">
                       <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-blue-600 transition-colors">FinTech Dashboard</h3>
                       <p class="text-slate-600 mb-6 text-sm leading-relaxed">
                           A comprehensive financial analytics dashboard featuring real-time data visualization using Chart.js and React.
                       </p>
                       <div class="flex gap-3">
                           <a href="#" class="flex-1 text-center py-2 rounded-lg bg-slate-100 text-slate-900 font-medium text-sm hover:bg-slate-200 transition-colors">Code</a>
                           <a href="#" class="flex-1 text-center py-2 rounded-lg bg-blue-600 text-white font-medium text-sm hover:bg-blue-700 transition-colors shadow-lg shadow-blue-500/30">Live Demo</a>
                       </div>
                   </div>
               </div>

               <!-- Project Card 2 -->
               <div class="group bg-white rounded-2xl overflow-hidden shadow-lg border border-slate-100 hover:shadow-2xl transition-all duration-300 hover:-translate-y-2 reveal delay-100">
                   <div class="relative h-64 overflow-hidden">
                       <div class="absolute inset-0 bg-slate-900/20 group-hover:bg-slate-900/0 transition-colors z-10"></div>
                       <img src="https://images.unsplash.com/photo-1522542550221-31fd19575a2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="E-commerce" class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700">
                       <div class="absolute top-4 right-4 z-20 bg-white/90 backdrop-blur px-3 py-1 rounded-full text-xs font-bold text-slate-900 shadow-sm">
                           MERN Stack
                       </div>
                   </div>
                   <div class="p-8">
                       <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-blue-600 transition-colors">Luxe Commerce</h3>
                       <p class="text-slate-600 mb-6 text-sm leading-relaxed">
                           Full-stack e-commerce platform with user authentication, payment integration (Stripe), and admin panel.
                       </p>
                       <div class="flex gap-3">
                           <a href="#" class="flex-1 text-center py-2 rounded-lg bg-slate-100 text-slate-900 font-medium text-sm hover:bg-slate-200 transition-colors">Code</a>
                           <a href="#" class="flex-1 text-center py-2 rounded-lg bg-blue-600 text-white font-medium text-sm hover:bg-blue-700 transition-colors shadow-lg shadow-blue-500/30">Live Demo</a>
                       </div>
                   </div>
               </div>

               <!-- Project Card 3 -->
               <div class="group bg-white rounded-2xl overflow-hidden shadow-lg border border-slate-100 hover:shadow-2xl transition-all duration-300 hover:-translate-y-2 reveal delay-200">
                   <div class="relative h-64 overflow-hidden">
                       <div class="absolute inset-0 bg-slate-900/20 group-hover:bg-slate-900/0 transition-colors z-10"></div>
                       <img src="https://images.unsplash.com/photo-1611162617474-5b21e879e113?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Social App" class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700">
                       <div class="absolute top-4 right-4 z-20 bg-white/90 backdrop-blur px-3 py-1 rounded-full text-xs font-bold text-slate-900 shadow-sm">
                           Next.js
                       </div>
                   </div>
                   <div class="p-8">
                       <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-blue-600 transition-colors">Connect Social</h3>
                       <p class="text-slate-600 mb-6 text-sm leading-relaxed">
                           A real-time social media application featuring instant messaging, notifications, and dynamic feeds.
                       </p>
                       <div class="flex gap-3">
                           <a href="#" class="flex-1 text-center py-2 rounded-lg bg-slate-100 text-slate-900 font-medium text-sm hover:bg-slate-200 transition-colors">Code</a>
                           <a href="#" class="flex-1 text-center py-2 rounded-lg bg-blue-600 text-white font-medium text-sm hover:bg-blue-700 transition-colors shadow-lg shadow-blue-500/30">Live Demo</a>
                       </div>
                   </div>
               </div>
           </div>
           
           <div class="mt-12 text-center md:hidden">
                <a href="#" class="inline-flex items-center gap-2 text-slate-900 font-bold hover:text-blue-600 transition-colors">
                   View Github <i class="fas fa-arrow-right"></i>
               </a>
           </div>
       </div>
   </section>

   <!-- Contact Section -->
   <section id="contact" class="py-24 bg-slate-900 text-white relative overflow-hidden">
       <!-- Decorative Elements -->
       <div class="absolute top-0 right-0 w-64 h-64 bg-blue-600 rounded-full mix-blend-overlay filter blur-3xl opacity-20"></div>
       <div class="absolute bottom-0 left-0 w-64 h-64 bg-cyan-600 rounded-full mix-blend-overlay filter blur-3xl opacity-20"></div>

       <div class="container mx-auto px-6 relative z-10">
           <div class="grid md:grid-cols-2 gap-16">
               <div class="reveal">
                   <h3 class="text-cyan-400 font-bold tracking-wider uppercase mb-2">Get In Touch</h3>
                   <h2 class="text-4xl md:text-5xl font-display font-bold mb-6">Let's start a project together</h2>
                   <p class="text-slate-400 text-lg mb-8">
                       Interested in working together? Fill out the form or send me an email. I'm always open to discussing new projects, creative ideas or opportunities to be part of your visions.
                   </p>
                   
                   <div class="space-y-6">
                       <div class="flex items-center gap-4">
                           <div class="w-12 h-12 rounded-full bg-slate-800 flex items-center justify-center text-cyan-400 text-xl">
                               <i class="fas fa-envelope"></i>
                           </div>
                           <div>
                               <p class="text-sm text-slate-400">Email Me</p>
                               <p class="font-medium">rathnayakadivan@gmail.com</p>
                           </div>
                       </div>
                       <div class="flex items-center gap-4">
                           <div class="w-12 h-12 rounded-full bg-slate-800 flex items-center justify-center text-cyan-400 text-xl">
                               <i class="fas fa-map-marker-alt"></i>
                           </div>
                           <div>
                               <p class="text-sm text-slate-400">Location</p>
                               <p class="font-medium">Colombo, Sri Lanka</p>
                           </div>
                       </div>
                   </div>

                   <div class="flex gap-4 mt-10">
                       <a href="#" class="w-10 h-10 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors"><i class="fab fa-github"></i></a>
                       <a href="#" class="w-10 h-10 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors"><i class="fab fa-linkedin-in"></i></a>
                       <a href="#" class="w-10 h-10 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors"><i class="fab fa-twitter"></i></a>
                       <a href="#" class="w-10 h-10 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors"><i class="fab fa-instagram"></i></a>
                   </div>
               </div>

               <div class="bg-white rounded-2xl p-8 text-slate-800 reveal delay-100">
                   <form id="contact-form" class="space-y-6">
                       <div>
                           <label for="name" class="block text-sm font-bold text-slate-700 mb-2">Your Name</label>
                           <input type="text" id="name" class="w-full px-4 py-3 rounded-lg bg-slate-50 border border-slate-200 focus:border-blue-500 focus:ring-2 focus:ring-blue-200 outline-none transition-all" placeholder="John Doe" required>
                       </div>
                       <div>
                           <label for="email" class="block text-sm font-bold text-slate-700 mb-2">Email Address</label>
                           <input type="email" id="email" class="w-full px-4 py-3 rounded-lg bg-slate-50 border border-slate-200 focus:border-blue-500 focus:ring-2 focus:ring-blue-200 outline-none transition-all" placeholder="john@example.com" required>
                       </div>
                       <div>
                           <label for="message" class="block text-sm font-bold text-slate-700 mb-2">Message</label>
                           <textarea id="message" rows="4" class="w-full px-4 py-3 rounded-lg bg-slate-50 border border-slate-200 focus:border-blue-500 focus:ring-2 focus:ring-blue-200 outline-none transition-all resize-none" placeholder="Tell me about your project..." required></textarea>
                       </div>
                       <button type="submit" class="w-full py-4 bg-blue-600 text-white font-bold rounded-lg hover:bg-blue-700 transition-all shadow-lg shadow-blue-500/30 transform hover:-translate-y-1">
                           Send Message <i class="fas fa-paper-plane ml-2"></i>
                       </button>
                   </form>
                   <!-- Success Message (Hidden by default) -->
                   <div id="success-msg" class="hidden text-center py-10">
                       <div class="w-16 h-16 bg-green-100 text-green-500 rounded-full flex items-center justify-center text-2xl mx-auto mb-4">
                           <i class="fas fa-check"></i>
                       </div>
                       <h3 class="text-2xl font-bold text-slate-900 mb-2">Message Sent!</h3>
                       <p class="text-slate-600">Thanks for reaching out. I'll get back to you shortly.</p>
                       <button id="reset-btn" class="mt-6 text-blue-600 font-medium hover:underline">Send another</button>
                   </div>
               </div>
           </div>
       </div>
   </section>

   <!-- Footer -->
   <footer class="bg-slate-950 text-slate-400 py-8 border-t border-slate-900">
       <div class="container mx-auto px-6 flex flex-col md:flex-row justify-between items-center">
           <div class="mb-4 md:mb-0">
               <span class="text-xl font-display font-bold text-white">Divan<span class="text-blue-600">.</span></span>
               <span class="ml-2 text-sm">&copy; 2023 All Rights Reserved.</span>
           </div>
           <div class="flex gap-6 text-sm">
               <a href="#" class="hover:text-white transition-colors">Privacy Policy</a>
               <a href="#" class="hover:text-white transition-colors">Terms of Service</a>
           </div>
       </div>
   </footer>

   <!-- JavaScript Logic -->
   <script>
       document.addEventListener('DOMContentLoaded', () => {
           
           // 1. Navbar Scroll Effect
           const navbar = document.getElementById('navbar');
           window.addEventListener('scroll', () => {
               if (window.scrollY > 50) {
                   navbar.classList.add('glass-nav', 'shadow-sm');
                   navbar.classList.remove('py-4');
                   navbar.classList.add('py-2');
               } else {
                   navbar.classList.remove('glass-nav', 'shadow-sm', 'py-2');
                   navbar.classList.add('py-4');
               }
           });

           // 2. Mobile Menu Toggle
           const btn = document.getElementById('mobile-menu-btn');
           const menu = document.getElementById('mobile-menu');

           btn.addEventListener('click', () => {
               menu.classList.toggle('hidden');
           });

           // Close mobile menu when clicking a link
           menu.querySelectorAll('a').forEach(link => {
               link.addEventListener('click', () => {
                   menu.classList.add('hidden');
               });
           });

           // 3. Intersection Observer for Scroll Animations
           const observerOptions = {
               threshold: 0.1,
               rootMargin: "0px 0px -50px 0px"
           };

           const observer = new IntersectionObserver((entries) => {
               entries.forEach(entry => {
                   if (entry.isIntersecting) {
                       entry.target.classList.add('active');
                       
                       // Trigger Skill Bars if inside the section
                       const skillFills = entry.target.querySelectorAll('.skill-fill');
                       skillFills.forEach(fill => {
                           fill.style.width = fill.getAttribute('data-width');
                       });

                       observer.unobserve(entry.target);
                   }
               });
           }, observerOptions);

           document.querySelectorAll('.reveal').forEach(el => {
               observer.observe(el);
           });

           // 4. Contact Form Handling
           const form = document.getElementById('contact-form');
           const successMsg = document.getElementById('success-msg');
           const resetBtn = document.getElementById('reset-btn');

           form.addEventListener('submit', (e) => {
               e.preventDefault();
               // Simulate API call
               const btn = form.querySelector('button');
               const originalText = btn.innerHTML;
               
               btn.disabled = true;
               btn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Sending...';

               setTimeout(() => {
                   form.style.display = 'none';
                   successMsg.classList.remove('hidden');
                   successMsg.classList.add('animate-fade-in-up');
                   btn.disabled = false;
                   btn.innerHTML = originalText;
                   form.reset();
               }, 1500);
           });

           resetBtn.addEventListener('click', () => {
               successMsg.classList.add('hidden');
               form.style.display = 'block';
               form.classList.add('animate-fade-in-up');
           });
       });
   </script>
</body>
</html>
