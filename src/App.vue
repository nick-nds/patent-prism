<script setup>
import { ref, onMounted } from 'vue'

const activeSection = ref('overview');
const isLoaded = ref(false);
const hoveredBenefit = ref(null);
const hoveredTech = ref(null);

const qualifications = ref([
  { text: "Cross-functional ability to switch between front-end, back-end, and dev-ops contexts", icon: "⚡" },
  { text: "Fluent in PHP with professional experience", icon: "🔧" },
  { text: "Extensive Laravel experience is a requirement", icon: "🚀" },
  { text: "Excitement to follow Laravel best practices", icon: "✨" },
  { text: "Familiarity with ES Next JavaScript (Vue.js, Node, Vite)", icon: "💻" },
  { text: "Experience with Tailwind CSS utility classes preferred", icon: "🎨" },
  { text: "Experience with ElasticSearch, Redis, GraphQL is a plus", icon: "🔍" },
  { text: "Background in NLP, transcription engines, and neural networks is advantageous", icon: "🧠" },
  { text: "Strong understanding of RESTful API design, permissions, and ACL principles", icon: "🔐" },
  { text: "Comfort working with Unix command line tools", icon: "⚡" },
  { text: "Strong knowledge of Git/version control", icon: "🌿" },
  { text: "Experience with Scrum/Agile methodologies", icon: "🔄" },
  { text: "Excellent written and verbal communication skills", icon: "💬" }
]);

const benefits = ref([
  { icon: "💰", title: "401(k)", desc: "Retirement planning support", color: "bg-slate-50 hover:bg-slate-100" },
  { icon: "🦷", title: "Dental Insurance", desc: "Comprehensive dental coverage", color: "bg-slate-50 hover:bg-slate-100" },
  { icon: "💳", title: "Flexible Spending", desc: "FSA for healthcare expenses", color: "bg-slate-50 hover:bg-slate-100" },
  { icon: "🏥", title: "Health Insurance", desc: "Company-subsidized medical", color: "bg-slate-50 hover:bg-slate-100" },
  { icon: "💊", title: "Health Savings", desc: "HSA with employer contributions", color: "bg-slate-50 hover:bg-slate-100" },
  { icon: "🛡️", title: "Life Insurance", desc: "Protection for your family", color: "bg-slate-50 hover:bg-slate-100" },
  { icon: "🏖️", title: "Paid Time Off", desc: "Flexible vacation policy", color: "bg-slate-50 hover:bg-slate-100" },
  { icon: "👁️", title: "Vision Insurance", desc: "Complete eye care coverage", color: "bg-slate-50 hover:bg-slate-100" }
]);

const softSkills = ref([
  { title: "Discipline", desc: "Concerning delivery dates", icon: "⏰" },
  { title: "Clean Code", desc: "Appreciation for readable code", icon: "✨" },
  { title: "Documentation", desc: "Commitment to proper documentation", icon: "📚" }
]);

const techStack = ref([
  { 
    name: "Laravel", 
    category: "Backend Framework",
    description: "PHP framework for robust web applications",
    icon: "🚀",
    accent: "border-blue-200 bg-blue-50"
  },
  { 
    name: "Vue.js", 
    category: "Frontend Framework",
    description: "Progressive JavaScript framework for UIs",
    icon: "⚡",
    accent: "border-emerald-200 bg-emerald-50"
  },
  { 
    name: "PHP", 
    category: "Backend Language",
    description: "Server-side scripting for web development",
    icon: "🔧",
    accent: "border-indigo-200 bg-indigo-50"
  },
  { 
    name: "JavaScript", 
    category: "Programming Language",
    description: "Dynamic language for modern web apps",
    icon: "💻",
    accent: "border-yellow-200 bg-yellow-50"
  },
  { 
    name: "Tailwind CSS", 
    category: "CSS Framework",
    description: "Utility-first CSS for rapid UI development",
    icon: "🎨",
    accent: "border-cyan-200 bg-cyan-50"
  },
  { 
    name: "NLP & AI", 
    category: "Core Technology",
    description: "Natural language processing and machine learning",
    icon: "🧠",
    accent: "border-purple-200 bg-purple-50"
  },
  { 
    name: "ElasticSearch", 
    category: "Search Engine",
    description: "Distributed search and analytics engine",
    icon: "🔍",
    accent: "border-orange-200 bg-orange-50"
  },
  { 
    name: "Redis", 
    category: "Data Store",
    description: "In-memory data structure store",
    icon: "⚡",
    accent: "border-red-200 bg-red-50"
  },
  { 
    name: "GraphQL", 
    category: "API Technology",
    description: "Query language for APIs",
    icon: "🔗",
    accent: "border-pink-200 bg-pink-50"
  }
]);

onMounted(() => {
  setTimeout(() => {
    isLoaded.value = true;
  }, 100);
});

const scrollToSection = (sectionId) => {
  activeSection.value = sectionId;
  const element = document.getElementById(sectionId);
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<template>
  <div class="min-h-screen bg-white">
    <!-- Hero Section -->
    <section class="relative bg-slate-900 overflow-hidden">
      <!-- Neural Network Background Pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute top-20 left-20 w-40 h-40 bg-blue-500 rounded-full animate-pulse"></div>
        <div class="absolute bottom-32 right-32 w-56 h-56 bg-indigo-500 rounded-full animate-pulse"></div>
        <div class="absolute top-1/2 left-1/3 w-32 h-32 bg-purple-500 rounded-full animate-pulse"></div>
        <!-- Connection lines -->
        <svg class="absolute inset-0 w-full h-full" viewBox="0 0 800 600">
          <line x1="100" y1="100" x2="300" y2="200" stroke="url(#gradient1)" stroke-width="1" opacity="0.3"/>
          <line x1="300" y1="200" x2="500" y2="150" stroke="url(#gradient1)" stroke-width="1" opacity="0.3"/>
          <line x1="500" y1="150" x2="700" y2="300" stroke="url(#gradient1)" stroke-width="1" opacity="0.3"/>
          <defs>
            <linearGradient id="gradient1" x1="0%" y1="0%" x2="100%" y2="0%">
              <stop offset="0%" style="stop-color:#3b82f6;stop-opacity:1" />
              <stop offset="100%" style="stop-color:#8b5cf6;stop-opacity:1" />
            </linearGradient>
          </defs>
        </svg>
      </div>

      <div class="relative z-10 px-6 py-24">
        <div class="max-w-6xl mx-auto">
          <!-- Company Header -->
          <div class="text-center mb-16" :class="{ 'animate-fade-in': isLoaded }">
            <div class="flex justify-center items-center mb-8">
              <div class="relative">
                <div class="text-5xl mr-6 animate-pulse">🧠</div>
                <div class="absolute -inset-2 bg-blue-500/20 rounded-full blur-lg"></div>
              </div>
              <div>
                <h1 class="text-4xl md:text-6xl font-bold text-white mb-2">
                  Patent <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-purple-400">Prism</span>
                </h1>
                <div class="flex items-center justify-center space-x-2 text-slate-400">
                  <div class="w-2 h-2 bg-blue-400 rounded-full animate-pulse"></div>
                  <span class="text-sm font-medium">AI-Powered Healthcare Solutions</span>
                  <div class="w-2 h-2 bg-purple-400 rounded-full animate-pulse"></div>
                </div>
              </div>
            </div>
          </div>

          <!-- Job Title -->
          <div class="text-center mb-16">
            <div class="inline-flex items-center bg-white/5 backdrop-blur-sm border border-white/10 rounded-full px-6 py-2 mb-6">
              <span class="w-2 h-2 bg-green-400 rounded-full mr-3 animate-pulse"></span>
              <span class="text-green-400 font-medium">We're hiring</span>
            </div>
            <h2 class="text-3xl md:text-5xl font-bold text-white mb-6">
              Software Developer
            </h2>
            <p class="text-lg md:text-xl text-slate-300 max-w-3xl mx-auto leading-relaxed mb-8">
              Join our team of innovators building the future of healthcare technology with 
              <span class="text-blue-400 font-semibold">Natural Language Processing</span> and 
              <span class="text-purple-400 font-semibold">Machine Learning</span>
            </p>
            <div class="flex flex-col sm:flex-row gap-4 justify-center">
              <button @click="scrollToSection('apply')" 
                      class="bg-blue-600 hover:bg-blue-700 text-white font-semibold py-3 px-8 rounded-lg transition-all duration-300 transform hover:scale-105">
                Apply Now
              </button>
              <button @click="scrollToSection('overview')" 
                      class="border border-white/20 text-white hover:bg-white/5 font-semibold py-3 px-8 rounded-lg transition-all duration-300">
                Learn More
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Navigation -->
    <nav class="sticky top-0 bg-white/90 backdrop-blur-sm border-b border-slate-200 z-50">
      <div class="max-w-6xl mx-auto px-6">
        <div class="flex justify-center space-x-8 py-4">
          <button @click="scrollToSection('overview')" 
                  :class="activeSection === 'overview' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-slate-600 hover:text-slate-900'"
                  class="font-medium pb-2 transition-colors">
            Overview
          </button>
          <button @click="scrollToSection('tech-stack')" 
                  :class="activeSection === 'tech-stack' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-slate-600 hover:text-slate-900'"
                  class="font-medium pb-2 transition-colors">
            Tech Stack
          </button>
          <button @click="scrollToSection('qualifications')" 
                  :class="activeSection === 'qualifications' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-slate-600 hover:text-slate-900'"
                  class="font-medium pb-2 transition-colors">
            Requirements
          </button>
          <button @click="scrollToSection('benefits')" 
                  :class="activeSection === 'benefits' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-slate-600 hover:text-slate-900'"
                  class="font-medium pb-2 transition-colors">
            Benefits
          </button>
        </div>
      </div>
    </nav>

    <!-- Overview Section -->
    <section id="overview" class="py-20 px-6 bg-slate-50">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-16">
          <h3 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6">Why Patent Prism?</h3>
          <p class="text-xl text-slate-600 max-w-3xl mx-auto leading-relaxed">
            For over 10 years, we've been pioneering AI-powered healthcare solutions, 
            making us one of the first companies to apply NLP in healthcare.
          </p>
        </div>

        <div class="grid md:grid-cols-3 gap-8 mb-16">
          <div class="bg-white p-8 rounded-xl border border-slate-200 hover:shadow-lg transition-all duration-300">
            <div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mb-6">
              <span class="text-2xl">🏥</span>
            </div>
            <h4 class="text-xl font-bold text-slate-900 mb-4">Healthcare Focus</h4>
            <p class="text-slate-600 leading-relaxed">
              Optimizing sales, marketing, and operations within the healthcare industry 
              through cutting-edge AI technology.
            </p>
          </div>
          <div class="bg-white p-8 rounded-xl border border-slate-200 hover:shadow-lg transition-all duration-300">
            <div class="w-12 h-12 bg-purple-100 rounded-lg flex items-center justify-center mb-6">
              <span class="text-2xl">🧠</span>
            </div>
            <h4 class="text-xl font-bold text-slate-900 mb-4">AI Innovation</h4>
            <p class="text-slate-600 leading-relaxed">
              Leading-edge natural language processing and machine learning 
              to provide actionable insights in real-time.
            </p>
          </div>
          <div class="bg-white p-8 rounded-xl border border-slate-200 hover:shadow-lg transition-all duration-300">
            <div class="w-12 h-12 bg-emerald-100 rounded-lg flex items-center justify-center mb-6">
              <span class="text-2xl">⚡</span>
            </div>
            <h4 class="text-xl font-bold text-slate-900 mb-4">Real-time Impact</h4>
            <p class="text-slate-600 leading-relaxed">
              Within 1 minute of a lead, customers get actionable intelligence 
              to increase revenue and lower acquisition costs.
            </p>
          </div>
        </div>

        <!-- AI/ML Stats -->
        <div class="bg-white rounded-xl border border-slate-200 p-8">
          <div class="grid md:grid-cols-4 gap-8 text-center">
            <div>
              <div class="text-3xl font-bold text-blue-600 mb-2">10+</div>
              <div class="text-slate-600">Years in Healthcare AI</div>
            </div>
            <div>
              <div class="text-3xl font-bold text-purple-600 mb-2">&lt;1min</div>
              <div class="text-slate-600">AI Response Time</div>
            </div>
            <div>
              <div class="text-3xl font-bold text-emerald-600 mb-2">99.9%</div>
              <div class="text-slate-600">System Uptime</div>
            </div>
            <div>
              <div class="text-3xl font-bold text-orange-600 mb-2">24/7</div>
              <div class="text-slate-600">AI Processing</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Tech Stack Section -->
    <section id="tech-stack" class="py-20 px-6">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-16">
          <h3 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6">Our Tech Stack</h3>
          <p class="text-xl text-slate-600">Modern technologies powering healthcare innovation</p>
        </div>
        
        <!-- Core Technologies Grid -->
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6 mb-12">
          <div v-for="(tech, index) in techStack" :key="tech.name" 
               @mouseenter="hoveredTech = index"
               @mouseleave="hoveredTech = null"
               class="bg-white border border-slate-200 rounded-xl p-6 hover:shadow-lg transition-all duration-300 transform hover:-translate-y-1"
               :class="[tech.accent, hoveredTech === index ? 'border-slate-300' : '']">
            <div class="flex items-start space-x-4">
              <div class="text-3xl" :class="{ 'animate-bounce': hoveredTech === index }">{{ tech.icon }}</div>
              <div class="flex-1">
                <div class="flex items-center justify-between mb-2">
                  <h5 class="text-lg font-bold text-slate-900">{{ tech.name }}</h5>
                  <span class="px-2 py-1 text-xs rounded-full bg-slate-100 text-slate-600">
                    {{ tech.category }}
                  </span>
                </div>
                <p class="text-slate-600 text-sm leading-relaxed">{{ tech.description }}</p>
              </div>
            </div>
          </div>
        </div>

        <!-- AI/ML Focus Box -->
        <div class="bg-gradient-to-r from-slate-900 to-slate-800 rounded-xl p-8 text-white">
          <div class="text-center mb-8">
            <div class="text-4xl mb-4">🤖</div>
            <h4 class="text-2xl font-bold mb-4">AI & Machine Learning at the Core</h4>
            <p class="text-slate-300 max-w-2xl mx-auto">
              Our platform leverages advanced NLP algorithms, neural networks, and real-time processing 
              to transform healthcare data into actionable insights.
            </p>
          </div>
          <div class="grid md:grid-cols-3 gap-6">
            <div class="text-center">
              <div class="w-12 h-12 bg-blue-500/20 rounded-lg flex items-center justify-center mx-auto mb-4">
                <span class="text-xl">🧠</span>
              </div>
              <h5 class="font-semibold mb-2">Natural Language Processing</h5>
              <p class="text-sm text-slate-400">Advanced text analysis and understanding</p>
            </div>
            <div class="text-center">
              <div class="w-12 h-12 bg-purple-500/20 rounded-lg flex items-center justify-center mx-auto mb-4">
                <span class="text-xl">⚡</span>
              </div>
              <h5 class="font-semibold mb-2">Real-time Processing</h5>
              <p class="text-sm text-slate-400">Instant insights and recommendations</p>
            </div>
            <div class="text-center">
              <div class="w-12 h-12 bg-emerald-500/20 rounded-lg flex items-center justify-center mx-auto mb-4">
                <span class="text-xl">🎯</span>
              </div>
              <h5 class="font-semibold mb-2">Predictive Analytics</h5>
              <p class="text-sm text-slate-400">Machine learning predictions and trends</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Qualifications Section -->
    <section id="qualifications" class="py-20 px-6 bg-slate-50">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-16">
          <h3 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6">What We're Looking For</h3>
          <p class="text-xl text-slate-600">
            Cross-functional developers who thrive in every aspect of our codebase
          </p>
        </div>
        
        <div class="grid md:grid-cols-2 gap-6 mb-12">
          <div v-for="(qual, index) in qualifications" :key="index"
               class="bg-white p-6 rounded-xl border border-slate-200 hover:shadow-md transition-all duration-300">
            <div class="flex items-start space-x-4">
              <div class="text-xl text-slate-400">{{ qual.icon }}</div>
              <p class="text-slate-700 leading-relaxed">{{ qual.text }}</p>
            </div>
          </div>
        </div>

        <!-- Key Requirements Highlight -->
        <div class="bg-blue-50 border border-blue-200 rounded-xl p-8">
          <h4 class="text-xl font-bold text-slate-900 mb-6 text-center">Must-Have Experience</h4>
          <div class="grid md:grid-cols-2 gap-6">
            <div class="flex items-center space-x-3">
              <div class="w-8 h-8 bg-blue-100 rounded-full flex items-center justify-center">
                <span class="text-blue-600 font-bold text-sm">2+</span>
              </div>
              <span class="text-slate-700">Years of Laravel experience</span>
            </div>
            <div class="flex items-center space-x-3">
              <div class="w-8 h-8 bg-emerald-100 rounded-full flex items-center justify-center">
                <span class="text-emerald-600 font-bold text-sm">2+</span>
              </div>
              <span class="text-slate-700">Years of Vue.js experience</span>
            </div>
            <div class="flex items-center space-x-3">
              <div class="w-8 h-8 bg-purple-100 rounded-full flex items-center justify-center">
                <span class="text-purple-600 text-sm">🧠</span>
              </div>
              <span class="text-slate-700">Interest in AI/NLP technologies</span>
            </div>
            <div class="flex items-center space-x-3">
              <div class="w-8 h-8 bg-orange-100 rounded-full flex items-center justify-center">
                <span class="text-orange-600 text-sm">💬</span>
              </div>
              <span class="text-slate-700">Strong English communication</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Values Section -->
    <section class="py-20 px-6">
      <div class="max-w-4xl mx-auto">
        <div class="text-center mb-16">
          <h3 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6">Our Values</h3>
          <p class="text-xl text-slate-600">What drives us every day</p>
        </div>
        <div class="grid md:grid-cols-3 gap-8">
          <div v-for="skill in softSkills" :key="skill.title"
               class="text-center p-8 bg-white border border-slate-200 rounded-xl hover:shadow-md transition-all duration-300">
            <div class="w-16 h-16 bg-slate-100 rounded-full flex items-center justify-center mx-auto mb-6">
              <span class="text-2xl">{{ skill.icon }}</span>
            </div>
            <h4 class="text-xl font-bold text-slate-900 mb-3">{{ skill.title }}</h4>
            <p class="text-slate-600">{{ skill.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Benefits Section -->
    <section id="benefits" class="py-20 px-6 bg-slate-50">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-16">
          <h3 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6">Comprehensive Benefits</h3>
          <p class="text-xl text-slate-600">We take care of our team so they can focus on innovation</p>
        </div>
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
          <div v-for="(benefit, index) in benefits" :key="index"
               @mouseenter="hoveredBenefit = index"
               @mouseleave="hoveredBenefit = null"
               class="p-6 rounded-xl transition-all duration-300 cursor-pointer transform hover:-translate-y-1 border border-slate-200"
               :class="benefit.color">
            <div class="text-2xl mb-4" 
                 :class="{ 'animate-bounce': hoveredBenefit === index }">
              {{ benefit.icon }}
            </div>
            <h4 class="font-bold text-lg mb-2 text-slate-900">{{ benefit.title }}</h4>
            <p class="text-sm text-slate-600">{{ benefit.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Application Section -->
    <section id="apply" class="py-20 px-6 bg-slate-900">
      <div class="max-w-4xl mx-auto text-center">
        <h3 class="text-3xl md:text-4xl font-bold text-white mb-6">Ready to Join Us?</h3>
        <p class="text-xl text-slate-300 mb-12 max-w-2xl mx-auto leading-relaxed">
          Be part of a team that's revolutionizing healthcare through AI and NLP technology.
          Send us your resume and show us your best work!
        </p>
        
        <div class="bg-white/5 backdrop-blur-sm border border-white/10 rounded-xl p-8 mb-12">
          <div class="grid md:grid-cols-2 gap-8 text-left">
            <div>
              <h4 class="text-lg font-bold text-white mb-4 flex items-center">
                <span class="mr-2">📋</span> Application Requirements
              </h4>
              <ul class="space-y-3 text-slate-300">
                <li class="flex items-center"><span class="text-blue-400 mr-3">•</span>Laravel: 2+ years required</li>
                <li class="flex items-center"><span class="text-blue-400 mr-3">•</span>Vue.js: 2+ years required</li>
                <li class="flex items-center"><span class="text-blue-400 mr-3">•</span>English proficiency required</li>
                <li class="flex items-center"><span class="text-blue-400 mr-3">•</span>GitHub profile</li>
              </ul>
            </div>
            <div>
              <h4 class="text-lg font-bold text-white mb-4 flex items-center">
                <span class="mr-2">💼</span> Job Details
              </h4>
              <ul class="space-y-3 text-slate-300">
                <li class="flex items-center"><span class="text-emerald-400 mr-3">✓</span>Full-time position</li>
                <li class="flex items-center"><span class="text-emerald-400 mr-3">✓</span>100% Remote work</li>
                <li class="flex items-center"><span class="text-emerald-400 mr-3">✓</span>8-hour shift</li>
                <li class="flex items-center"><span class="text-emerald-400 mr-3">✓</span>Bonus opportunities</li>
              </ul>
            </div>
          </div>
        </div>

        <div class="space-y-6">
          <a href="mailto:larajobs@patentprism.com" 
             class="inline-flex items-center bg-blue-600 hover:bg-blue-700 text-white font-semibold py-4 px-12 rounded-lg text-lg transition-all duration-300 transform hover:scale-105 shadow-lg">
            <span class="mr-2">📧</span> Send Application
          </a>
          <p class="text-slate-400 text-sm">
            Email: <span class="text-blue-400 font-semibold">larajobs@patentprism.com</span>
          </p>
        </div>

        <div class="mt-12 text-slate-400 text-sm max-w-2xl mx-auto">
          <p class="mb-2">🌈 Patent Prism is an equal opportunity employer</p>
          <p>We encourage applications from women, people of color, people with disabilities, 
             members of the LGBTQ community, and other underrepresented groups.</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}

@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 0.6s ease-out;
}
</style>
