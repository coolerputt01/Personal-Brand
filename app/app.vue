```vue
<template>
  <div class="site">

    <!-- NAVIGATION -->
    <header class="nav" :class="{ scrolled: scrolled }">
      <div class="nav-inner">
        <a href="#" class="brand" @click.prevent="scrollTo('home')">
          <span class="brand-mark">K</span>
          <span>
            <strong>KIMONA</strong>
            <small>HANSON-AMOAH</small>
          </span>
        </a>

        <nav class="desktop-nav">
          <a href="#about">About</a>
          <a href="#wealth">Wealth</a>
          <a href="#real-estate">Real Estate</a>
          <a href="#education">Education</a>
          <a href="#speaking">Speaking</a>
        </nav>

        <button class="nav-cta" @click="openContact">
          Work With Kimona
          <span>↗</span>
        </button>

        <button class="mobile-menu" @click="mobileOpen = !mobileOpen">
          <span></span>
          <span></span>
        </button>
      </div>

      <div v-if="mobileOpen" class="mobile-nav">
        <a href="#about" @click="mobileOpen = false">About</a>
        <a href="#wealth" @click="mobileOpen = false">Wealth</a>
        <a href="#real-estate" @click="mobileOpen = false">Real Estate</a>
        <a href="#education" @click="mobileOpen = false">Education</a>
        <a href="#speaking" @click="mobileOpen = false">Speaking</a>
        <button @click="openContact(); mobileOpen = false">Work With Kimona ↗</button>
      </div>
    </header>

    <!-- HERO -->
    <main id="home">

      <section class="hero">
        <div class="hero-glow glow-one"></div>
        <div class="hero-glow glow-two"></div>

        <div class="hero-grid"></div>

        <div class="hero-content">
          <div class="eyebrow reveal">
            <span class="pulse-dot"></span>
            WEALTH • REAL ESTATE • BUSINESS
          </div>

          <h1 class="reveal delay-1">
            Build wealth.<br />
            <em>On purpose.</em>
          </h1>

          <p class="hero-copy reveal delay-2">
            Kimona Hanson-Amoah is a wealth-building strategist, real estate
            professional and entrepreneur helping people turn knowledge,
            property and multiple income streams into long-term wealth.
          </p>

          <div class="hero-actions reveal delay-3">
            <button class="primary-btn" @click="scrollTo('wealth')">
              Explore the wealth strategy
              <span>↓</span>
            </button>

            <button class="text-btn" @click="scrollTo('about')">
              Meet Kimona <span>→</span>
            </button>
          </div>

          <div class="hero-proof reveal delay-4">
            <div>
              <strong>7+</strong>
              <span>Income stream<br />mindset</span>
            </div>
            <div>
              <strong>3</strong>
              <span>Core wealth<br />pillars</span>
            </div>
            <div>
              <strong>1M</strong>
              <span>Lives she aims<br />to impact</span>
            </div>
          </div>
        </div>

        <!-- HERO VISUAL -->
        <div class="hero-visual reveal delay-2">
          <div class="portrait-frame">
  <div class="portrait-image">
    <img
      src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSA2vmFg6qU7gHdowa2xrDAD6Obn90HHIuXjjw-F__f1Q&s=10"
      alt="Kimona Hanson-Amoah"
    />

    <div class="portrait-overlay"></div>

    <div class="portrait-caption">
      <span class="portrait-line"></span>
      <div>
        <small>FOUNDER • INVESTOR • REALTOR</small>
        <strong>KIMONA<br />HANSON-AMOAH</strong>
      </div>
    </div>

    <div class="portrait-badge">
      <span>WEALTH</span>
      <b>BUILDER</b>
    </div>
  </div>

  <div class="portrait-corner top-left"></div>
  <div class="portrait-corner bottom-right"></div>
</div>
        </div>
      </section>

      <!-- MARQUEE -->
      <div class="marquee">
        <div class="marquee-track">
          <span>WEALTH BUILDING</span>
          <b>✦</b>
          <span>REAL ESTATE</span>
          <b>✦</b>
          <span>BUSINESS STRATEGY</span>
          <b>✦</b>
          <span>FINANCIAL EDUCATION</span>
          <b>✦</b>
          <span>MULTIPLE INCOME STREAMS</span>
          <b>✦</b>
          <span>WEALTH BUILDING</span>
          <b>✦</b>
          <span>REAL ESTATE</span>
          <b>✦</b>
          <span>BUSINESS STRATEGY</span>
          <b>✦</b>
        </div>
      </div>

      <!-- ABOUT -->
      <section id="about" class="section about-section">
        <div class="section-label">01 — THE WOMAN BEHIND THE MISSION</div>

        <div class="about-grid">
          <div>
            <h2>
              More than a realtor.<br />
              <span>A wealth strategist.</span>
            </h2>
          </div>

          <div class="about-text">
            <p class="large">
              Kimona Hanson-Amoah built her brand around one powerful idea:
              wealth shouldn't depend on a single paycheck.
            </p>

            <p>
              Through real estate, investing, entrepreneurship and education,
              Kimona helps people understand the different vehicles available
              for building sustainable income and long-term wealth.
            </p>

            <button class="outline-btn" @click="aboutExpanded = !aboutExpanded">
              {{ aboutExpanded ? 'Show less' : 'Her story' }}
              <span>{{ aboutExpanded ? '↑' : '↗' }}</span>
            </button>

            <div v-if="aboutExpanded" class="expanded-story">
              <p>
                From pursuing financial freedom to becoming a real estate
                professional, entrepreneur and educator, Kimona's journey
                informs the straight-talk, practical approach behind her
                teaching.
              </p>
              <p>
                Her work spans real estate investing, stock-market education,
                business strategy and the creation of additional revenue
                streams.
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- WEALTH PILLARS -->
      <section id="wealth" class="section wealth-section">
        <div class="wealth-bg"></div>

        <div class="section-heading">
          <div>
            <div class="section-label light">02 — THE WEALTH FRAMEWORK</div>
            <h2>One goal.<br /><span>Multiple paths.</span></h2>
          </div>

          <p>
            Explore the areas where Kimona helps people move from earning
            money to intentionally building wealth.
          </p>
        </div>

        <div class="pillar-grid">
          <article
            v-for="(pillar, index) in pillars"
            :key="pillar.title"
            class="pillar"
            :class="{ active: activePillar === index }"
            @mouseenter="activePillar = index"
          >
            <div class="pillar-number">0{{ index + 1 }}</div>

            <div class="pillar-icon" v-html="pillar.icon"></div>

            <h3>{{ pillar.title }}</h3>

            <p>{{ pillar.description }}</p>

            <div class="pillar-footer">
              <span>{{ pillar.tag }}</span>
              <button @click="openPillar(pillar)">
                Explore <span>↗</span>
              </button>
            </div>
          </article>
        </div>
      </section>

      <!-- INTERACTIVE WEALTH MAP -->
      <section class="section strategy-section">
        <div class="section-label">03 — YOUR WEALTH MAP</div>

        <div class="strategy-heading">
          <h2>
            Where are you<br />
            <span>starting from?</span>
          </h2>

          <p>
            Choose a starting point to see the type of strategy Kimona's
            ecosystem can help you explore.
          </p>
        </div>

        <div class="strategy-container">

          <div class="strategy-options">
            <button
              v-for="option in strategyOptions"
              :key="option.id"
              :class="{ selected: selectedStrategy === option.id }"
              @click="selectedStrategy = option.id"
            >
              <span class="strategy-option-icon">{{ option.icon }}</span>
              <span>
                <small>START HERE</small>
                <strong>{{ option.title }}</strong>
              </span>
              <span class="arrow">→</span>
            </button>
          </div>

          <div class="strategy-result">
            <div class="result-top">
              <span>YOUR STARTING POINT</span>
              <div class="result-dot"></div>
            </div>

            <div class="result-content">
              <div class="result-icon">
                {{ currentStrategy.icon }}
              </div>

              <h3>{{ currentStrategy.title }}</h3>

              <p>{{ currentStrategy.description }}</p>

              <div class="result-path">
                <div
                  v-for="(step, index) in currentStrategy.steps"
                  :key="step"
                  class="path-step"
                >
                  <span>{{ index + 1 }}</span>
                  {{ step }}
                </div>
              </div>

              <button class="dark-btn" @click="openContact">
                Start a conversation <span>↗</span>
              </button>
            </div>
          </div>

        </div>
      </section>

      <!-- REAL ESTATE -->
      <section id="real-estate" class="section real-estate-section">
        <div class="real-estate-top">
          <div>
            <div class="section-label">04 — REAL ESTATE</div>
            <h2>
              Property can be<br />
              <span>a wealth engine.</span>
            </h2>
          </div>

          <div class="real-estate-copy">
            <p>
              From first-time homebuyers to investors exploring income
              properties, real estate is a central part of Kimona's wealth
              education ecosystem.
            </p>
            <button class="text-btn" @click="openContact">
              Explore real estate <span>↗</span>
            </button>
          </div>
        </div>

        <div class="property-showcase">
          <div
            v-for="(property, index) in properties"
            :key="property.title"
            class="property"
            :class="{ featured: index === 1 }"
          >
            <div class="property-image" :class="'property-' + index">
              <div class="property-overlay"></div>

              <span class="property-type">{{ property.type }}</span>

              <button class="property-expand" @click="openProperty(property)">
                ↗
              </button>

              <div class="property-bottom">
                <small>{{ property.location }}</small>
                <strong>{{ property.title }}</strong>
              </div>
            </div>

            <div class="property-meta">
              <span>{{ property.focus }}</span>
              <span>{{ property.action }} ↗</span>
            </div>
          </div>
        </div>
      </section>

      <!-- EDUCATION -->
      <section id="education" class="section education-section">
        <div class="section-heading education-heading">
          <div>
            <div class="section-label">05 — LEARN & BUILD</div>
            <h2>Knowledge that<br /><span>moves with you.</span></h2>
          </div>

          <p>
            Courses, guides, coaching and practical resources designed around
            wealth creation, real estate and business.
          </p>
        </div>

        <div class="education-grid">
          <article
            v-for="item in education"
            :key="item.title"
            class="education-card"
            @click="openEducation(item)"
          >
            <div class="education-top">
              <span>{{ item.category }}</span>
              <span class="education-arrow">↗</span>
            </div>

            <div class="education-icon" v-html="item.icon"></div>

            <h3>{{ item.title }}</h3>

            <p>{{ item.description }}</p>

            <div class="education-link">
              Explore resource <span>→</span>
            </div>
          </article>
        </div>
      </section>

      <!-- NUMBERS -->
      <section class="numbers-section">
        <div class="numbers-grid">
          <div v-for="stat in stats" :key="stat.label" class="stat">
            <strong>{{ stat.value }}</strong>
            <span>{{ stat.label }}</span>
          </div>
        </div>
      </section>

      <!-- TESTIMONIALS -->
      <section class="section testimonials-section">
        <div class="section-label">06 — FROM THE COMMUNITY</div>

        <div class="testimonial-layout">
          <div class="testimonial-intro">
            <h2>
              Knowledge is powerful.<br />
              <span>Applied knowledge changes lives.</span>
            </h2>

            <div class="testimonial-controls">
              <button @click="prevTestimonial">←</button>
              <span>{{ String(currentTestimonial + 1).padStart(2, '0') }} / 03</span>
              <button @click="nextTestimonial">→</button>
            </div>
          </div>

          <div class="testimonial-card">
            <div class="quote-mark">“</div>

            <p class="quote">
              {{ testimonials[currentTestimonial].quote }}
            </p>

            <div class="testimonial-person">
              <div class="avatar">
                {{ testimonials[currentTestimonial].initials }}
              </div>
              <div>
                <strong>{{ testimonials[currentTestimonial].name }}</strong>
                <span>{{ testimonials[currentTestimonial].role }}</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- SPEAKING -->
      <section id="speaking" class="speaking-section">
        <div class="speaking-grid"></div>

        <div class="speaking-content">
          <div class="section-label light">07 — BRING KIMONA TO YOUR STAGE</div>

          <h2>
            Your audience<br />
            deserves a <em>wealth</em><br />
            conversation.
          </h2>

          <p>
            Looking for a speaker who can make wealth, real estate,
            entrepreneurship and financial strategy practical and actionable?
          </p>

          <button class="primary-btn light-btn" @click="openContact">
            Book Kimona to speak
            <span>↗</span>
          </button>
        </div>

        <div class="speaking-side">
          <div class="event-card">
            <span>TOPICS</span>
            <div>
              <strong>Wealth Building</strong>
              <strong>Real Estate</strong>
              <strong>Multiple Income Streams</strong>
              <strong>Entrepreneurship</strong>
              <strong>Financial Strategy</strong>
            </div>
          </div>
        </div>
      </section>

      <!-- CTA -->
      <section class="final-cta">
        <div class="cta-circle circle-one"></div>
        <div class="cta-circle circle-two"></div>

        <div class="section-label">08 — TAKE THE NEXT STEP</div>

        <h2>
          Your next level<br />
          starts with a <span>strategy.</span>
        </h2>

        <p>
          Explore the resources, education and opportunities designed to help
          you build with intention.
        </p>

        <div class="cta-buttons">
          <button class="primary-btn" @click="openContact">
            Work with Kimona <span>↗</span>
          </button>

          <button class="outline-btn" @click="scrollTo('education')">
            Explore resources <span>↓</span>
          </button>
        </div>
      </section>

      <!-- FOOTER -->
      <footer>
        <div class="footer-main">
          <div class="footer-brand">
            <div class="brand">
              <span class="brand-mark">K</span>
              <span>
                <strong>KIMONA</strong>
                <small>HANSON-AMOAH</small>
              </span>
            </div>

            <p>
              Wealth strategist. Realtor. Entrepreneur. Educator.
            </p>
          </div>

          <div class="footer-links">
            <div>
              <span>EXPLORE</span>
              <a href="#about">About</a>
              <a href="#wealth">Wealth</a>
              <a href="#real-estate">Real Estate</a>
              <a href="#education">Education</a>
            </div>

            <div>
              <span>CONNECT</span>
              <a href="#" @click.prevent="openContact">Work With Me</a>
              <a href="#speaking">Speaking</a>
              <a href="#">Instagram ↗</a>
              <a href="#">YouTube ↗</a>
            </div>
          </div>
        </div>

        <div class="footer-bottom">
          <span>© {{ new Date().getFullYear() }} Kimona Hanson-Amoah</span>
          <span>Built around the business of extraordinary living.</span>
        </div>
      </footer>

    </main>

    <!-- CONTACT MODAL -->
    <Transition name="modal">
      <div v-if="contactOpen" class="modal-backdrop" @click.self="contactOpen = false">
        <div class="modal">
          <button class="modal-close" @click="contactOpen = false">×</button>

          <div class="section-label">LET'S CONNECT</div>

          <h2>What are you<br /><span>looking for?</span></h2>

          <div class="contact-options">
            <button
              v-for="option in contactOptions"
              :key="option.title"
              @click="contactSelection = option.title"
              :class="{ selected: contactSelection === option.title }"
            >
              <span>{{ option.icon }}</span>
              <div>
                <strong>{{ option.title }}</strong>
                <small>{{ option.description }}</small>
              </div>
              <b>→</b>
            </button>
          </div>

          <button
            class="dark-btn full-btn"
            :disabled="!contactSelection"
            @click="contactSubmitted = true"
          >
            {{ contactSubmitted ? 'Request received ✓' : 'Continue →' }}
          </button>

          <p v-if="contactSubmitted" class="success-message">
            This prototype would now route the visitor to the appropriate
            booking or contact flow.
          </p>
        </div>
      </div>
    </Transition>

    <!-- PILLAR MODAL -->
    <Transition name="modal">
      <div v-if="selectedPillar" class="modal-backdrop" @click.self="selectedPillar = null">
        <div class="modal pillar-modal">
          <button class="modal-close" @click="selectedPillar = null">×</button>

          <div class="pillar-icon large" v-html="selectedPillar.icon"></div>

          <div class="section-label">{{ selectedPillar.tag }}</div>

          <h2>{{ selectedPillar.title }}</h2>

          <p class="modal-description">
            {{ selectedPillar.longDescription }}
          </p>

          <div class="modal-list">
            <div v-for="item in selectedPillar.items" :key="item">
              <span>✓</span>
              {{ item }}
            </div>
          </div>

          <button class="dark-btn" @click="openContact(); selectedPillar = null">
            Explore this path <span>↗</span>
          </button>
        </div>
      </div>
    </Transition>

    <!-- PROPERTY MODAL -->
    <Transition name="modal">
      <div v-if="selectedProperty" class="modal-backdrop" @click.self="selectedProperty = null">
        <div class="modal property-modal">
          <button class="modal-close" @click="selectedProperty = null">×</button>

          <div class="modal-property-image" :class="'property-' + selectedProperty.index">
            <span>{{ selectedProperty.type }}</span>
          </div>

          <div class="section-label">{{ selectedProperty.focus }}</div>

          <h2>{{ selectedProperty.title }}</h2>

          <p>{{ selectedProperty.description }}</p>

          <button class="dark-btn" @click="openContact(); selectedProperty = null">
            Inquire about real estate <span>↗</span>
          </button>
        </div>
      </div>
    </Transition>

  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const scrolled = ref(false)
const mobileOpen = ref(false)
const aboutExpanded = ref(false)

const activePillar = ref(0)
const selectedStrategy = ref('beginner')

const contactOpen = ref(false)
const contactSelection = ref('')
const contactSubmitted = ref(false)

const selectedPillar = ref(null)
const selectedProperty = ref(null)
const selectedEducation = ref(null)

const currentTestimonial = ref(0)

const pillars = [
  {
    title: 'Real Estate',
    tag: 'PROPERTY WEALTH',
    description: 'Learn how property can become an asset, an income source and a long-term wealth vehicle.',
    longDescription: 'Real estate is one of the core areas of Kimona’s wealth-building philosophy, covering both homeownership and investment strategies.',
    items: ['First-time home buying', 'Investment properties', 'Wholesaling', 'Fix & flip strategies', 'Buy & hold concepts'],
    icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M3 11.5 12 4l9 7.5"/><path d="M5 10v10h14V10"/><path d="M9 20v-6h6v6"/></svg>`
  },
  {
    title: 'Investing',
    tag: 'MARKET KNOWLEDGE',
    description: 'Understand the fundamentals behind researching stocks and building an investment mindset.',
    longDescription: 'Kimona also teaches beginners how to approach the stock market with research, strategy and a long-term perspective.',
    items: ['Stock research fundamentals', 'Portfolio thinking', 'Investment education', 'Market fundamentals', 'Long-term wealth mindset'],
    icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M4 18V9"/><path d="M8 18V5"/><path d="M12 18v-7"/><path d="M16 18V3"/><path d="M20 18v-4"/><path d="M3 21h18"/></svg>`
  },
  {
    title: 'Business',
    tag: 'ENTREPRENEURSHIP',
    description: 'Turn your knowledge, skills and ideas into additional revenue streams.',
    longDescription: 'Beyond investing, Kimona helps entrepreneurs think strategically about their businesses and additional income opportunities.',
    items: ['Business fundamentals', 'Digital products', 'Revenue streams', 'Business strategy', 'Online growth'],
    icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><rect x="3" y="7" width="18" height="13" rx="2"/><path d="M8 7V5a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/><path d="M3 12h18"/><path d="M10 12v2h4v-2"/></svg>`
  }
]

const strategyOptions = [
  {
    id: 'beginner',
    icon: '01',
    title: 'I am just starting',
    description: 'Build a strong foundation before making major financial moves.',
    steps: ['Understand your money', 'Learn wealth fundamentals', 'Choose your first wealth vehicle']
  },
  {
    id: 'property',
    icon: '⌂',
    title: 'I want to buy property',
    description: 'Explore the fundamentals of becoming a homeowner or property investor.',
    steps: ['Prepare financially', 'Understand the market', 'Identify the right property']
  },
  {
    id: 'income',
    icon: '∞',
    title: 'I want more income',
    description: 'Explore the concept of building multiple income streams.',
    steps: ['Identify your skills', 'Create another revenue stream', 'Build systems around it']
  },
  {
    id: 'business',
    icon: '↗',
    title: 'I am building a business',
    description: 'Move from idea to strategy with stronger business fundamentals.',
    steps: ['Clarify your offer', 'Build your foundation', 'Create a growth strategy']
  }
]

const currentStrategy = computed(() => {
  return strategyOptions.find(x => x.id === selectedStrategy.value) || strategyOptions[0]
})

const properties = [
  {
    index: 0,
    title: 'The First Property',
    type: 'HOMEOWNERSHIP',
    location: 'STARTING THE JOURNEY',
    focus: 'HOMEOWNERSHIP',
    action: 'Learn more',
    description: 'A visual representation of the first step toward using real estate as part of a broader wealth strategy.'
  },
  {
    index: 1,
    title: 'The Investment',
    type: 'INVESTMENT',
    location: 'BUILDING ASSETS',
    focus: 'REAL ESTATE INVESTING',
    action: 'Explore',
    description: 'Explore the concepts behind buying, holding and strategically using investment property.'
  },
  {
    index: 2,
    title: 'The Portfolio',
    type: 'PORTFOLIO',
    location: 'LONG-TERM WEALTH',
    focus: 'PORTFOLIO BUILDING',
    action: 'Discover',
    description: 'The bigger picture: multiple properties and income-producing assets working together.'
  }
]

const education = [
  {
    category: 'STOCKS',
    title: 'Beginner’s Guide To Stock Investing',
    description: 'A practical starting point for learning how to research stocks and understand the market.',
    icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="m4 16 5-5 3 3 7-8"/><path d="M4 20h16"/></svg>`
  },
  {
    category: 'REAL ESTATE',
    title: 'Intro To Wholesaling',
    description: 'An introduction to one of the strategies used within the real estate investing ecosystem.',
    icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M3 11.5 12 4l9 7.5"/><path d="M5 10v10h14V10"/><path d="M9 20v-5h6v5"/></svg>`
  },
  {
    category: 'BUSINESS',
    title: 'Business Fundamentals',
    description: 'Develop stronger foundations for building and scaling an online business.',
    icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><circle cx="12" cy="12" r="8"/><path d="M12 8v4l3 2"/></svg>`
  },
  {
    category: 'WEALTH',
    title: 'Multiple Streams Of Income',
    description: 'Explore the thinking behind building several sources of revenue over time.',
    icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M4 17c3-5 5 2 8-3s5 2 8-4"/><circle cx="4" cy="17" r="1"/><circle cx="20" cy="10" r="1"/></svg>`
  }
]

const stats = [
  { value: '7+', label: 'Income-stream mindset' },
  { value: '1M', label: 'Lives targeted for impact' },
  { value: '$M+', label: 'Real estate production' },
  { value: '360°', label: 'Wealth perspective' }
]

const testimonials = [
  {
    quote: 'Kimona has a wealth of knowledge in real estate and genuinely wants everyone to succeed. Her approach makes complex concepts easier to understand.',
    name: 'Linda Washington',
    role: 'Client & Wealth Student',
    initials: 'LW'
  },
  {
    quote: 'The combination of coaching, live sessions and practical materials helped me start implementing what I learned across investing and multiple income streams.',
    name: 'Afua Osei',
    role: 'Wealth Coaching Student',
    initials: 'AO'
  },
  {
    quote: 'Her straight-talk approach and patience make the learning experience feel practical rather than overwhelming.',
    name: 'Wealth Builder',
    role: 'Community Member',
    initials: 'WB'
  }
]

const contactOptions = [
  {
    title: 'Real Estate',
    description: 'Home buying, property & investing',
    icon: '⌂'
  },
  {
    title: 'Business Strategy',
    description: 'Business growth & revenue streams',
    icon: '↗'
  },
  {
    title: 'Speaking',
    description: 'Bring Kimona to your event',
    icon: '◉'
  },
  {
    title: 'Wealth Education',
    description: 'Courses, coaching & resources',
    icon: '✦'
  }
]

function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({
    behavior: 'smooth'
  })
}

function openContact() {
  contactOpen.value = true
  contactSubmitted.value = false
}

function openPillar(pillar) {
  selectedPillar.value = pillar
}

function openProperty(property) {
  selectedProperty.value = property
}

function openEducation(item) {
  selectedEducation.value = item
  openContact()
}

function nextTestimonial() {
  currentTestimonial.value =
    (currentTestimonial.value + 1) % testimonials.length
}

function prevTestimonial() {
  currentTestimonial.value =
    (currentTestimonial.value - 1 + testimonials.length) %
    testimonials.length
}

function handleScroll() {
  scrolled.value = window.scrollY > 40
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:ital,wght@0,500;0,600;1,500;1,600&display=swap');

:root {
  --black: #0b0d0c;
  --dark: #101311;
  --cream: #f3efe7;
  --white: #ffffff;
  --gold: #c8a76a;
  --gold-light: #e4cb91;
  --muted: #858984;
  --line: rgba(255,255,255,.12);
  --dark-line: rgba(12,14,12,.12);
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  background: var(--cream);
  color: var(--black);
  font-family: 'DM Sans', sans-serif;
}

button,
a {
  font-family: inherit;
}

button {
  cursor: pointer;
}

.site {
  overflow: hidden;
}

/* NAV */

.nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  padding: 22px 5vw;
  transition: .35s ease;
}

.nav.scrolled {
  padding: 12px 5vw;
  background: rgba(11,13,12,.88);
  backdrop-filter: blur(18px);
  border-bottom: 1px solid rgba(255,255,255,.08);
}

.nav-inner {
  max-width: 1500px;
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.brand {
  display: flex;
  align-items: center;
  gap: 11px;
  color: white;
  text-decoration: none;
}

.brand-mark {
  width: 42px;
  height: 42px;
  display: grid;
  place-items: center;
  border: 1px solid rgba(200,167,106,.7);
  color: var(--gold-light);
  font-family: 'Playfair Display', serif;
  font-size: 22px;
}

.brand strong {
  display: block;
  font-size: 12px;
  letter-spacing: 3px;
}

.brand small {
  display: block;
  font-size: 7px;
  letter-spacing: 2px;
  color: var(--gold);
  margin-top: 3px;
}

.desktop-nav {
  display: flex;
  gap: 34px;
}

.desktop-nav a {
  color: rgba(255,255,255,.72);
  text-decoration: none;
  font-size: 11px;
  letter-spacing: 1px;
  transition: .25s;
}

.desktop-nav a:hover {
  color: white;
}

.nav-cta,
.primary-btn,
.dark-btn {
  border: none;
  background: var(--gold);
  color: #111;
  padding: 15px 20px;
  font-weight: 700;
  font-size: 11px;
  letter-spacing: .5px;
  display: inline-flex;
  align-items: center;
  gap: 18px;
  transition: .3s;
}

.nav-cta:hover,
.primary-btn:hover,
.dark-btn:hover {
  background: var(--gold-light);
  transform: translateY(-2px);
}

.mobile-menu {
  display: none;
  background: transparent;
  border: none;
}

.mobile-menu span {
  display: block;
  width: 24px;
  height: 1px;
  background: white;
  margin: 6px;
}

.mobile-nav {
  display: none;
}

/* HERO */

.hero {
  min-height: 100vh;
  position: relative;
  background: var(--black);
  color: white;
  display: grid;
  grid-template-columns: 1.05fr .95fr;
  align-items: center;
  padding: 130px 8vw 80px;
}

.hero-grid {
  position: absolute;
  inset: 0;
  opacity: .18;
  background-image:
    linear-gradient(rgba(255,255,255,.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,.06) 1px, transparent 1px);
  background-size: 80px 80px;
  mask-image: linear-gradient(to right, black, transparent 75%);
}

.hero-glow {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  pointer-events: none;
}

.glow-one {
  width: 400px;
  height: 400px;
  background: rgba(200,167,106,.1);
  top: 10%;
  right: 20%;
}

.glow-two {
  width: 250px;
  height: 250px;
  background: rgba(200,167,106,.06);
  bottom: 5%;
  left: 15%;
}

.hero-content {
  position: relative;
  z-index: 2;
  max-width: 700px;
}

.eyebrow,
.section-label {
  font-size: 9px;
  letter-spacing: 3px;
  font-weight: 700;
  color: var(--gold);
}

.eyebrow {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 25px;
}

.pulse-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--gold);
  box-shadow: 0 0 0 5px rgba(200,167,106,.1);
}

.hero h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(65px, 7vw, 120px);
  line-height: .88;
  font-weight: 500;
  letter-spacing: -5px;
}

.hero h1 em,
.hero h1 + .hero-copy em {
  color: var(--gold-light);
  font-weight: 500;
}

.hero-copy {
  max-width: 540px;
  color: #aeb2ad;
  font-size: 15px;
  line-height: 1.8;
  margin: 34px 0;
}

.hero-actions {
  display: flex;
  align-items: center;
  gap: 28px;
}

.text-btn {
  border: none;
  background: none;
  color: inherit;
  font-size: 11px;
  letter-spacing: 1px;
  display: inline-flex;
  align-items: center;
  gap: 10px;
}

.hero-proof {
  display: flex;
  gap: 35px;
  margin-top: 65px;
  padding-top: 25px;
  border-top: 1px solid var(--line);
}

.hero-proof div {
  display: flex;
  align-items: center;
  gap: 12px;
}

.hero-proof strong {
  color: var(--gold-light);
  font-family: 'Playfair Display', serif;
  font-size: 28px;
  font-weight: 500;
}

.hero-proof span {
  font-size: 8px;
  line-height: 1.5;
  color: #858984;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* HERO VISUAL */

.hero-visual {
  position: relative;
  min-height: 620px;
  display: grid;
  place-items: center;
}

/* =========================================
   PREMIUM PORTRAIT
========================================= */

.portrait-frame {
  width: min(450px, 75%);
  aspect-ratio: .75;
  position: relative;
  padding: 10px;
  background: rgba(200, 167, 106, .08);
  border: 1px solid rgba(200, 167, 106, .38);
  transition: transform .6s cubic-bezier(.2,.8,.2,1);
}

.portrait-frame:hover {
  transform: translateY(-8px) rotate(.4deg);
}

/* subtle gold line around the outside */

.portrait-frame::before {
  content: '';
  position: absolute;
  inset: -7px;
  border: 1px solid rgba(200, 167, 106, .12);
  pointer-events: none;
}

/* PHOTO */

.portrait-image {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  background: #181b18;
}

/* Actual image */

.portrait-image img {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;

  /*
    Adjust this if the Instagram profile image
    crops her face incorrectly.
  */
  object-position: center center;

  filter:
    saturate(.82)
    contrast(1.08)
    brightness(.88);

  transform: scale(1.04);
  transition:
    transform 1s cubic-bezier(.2,.8,.2,1),
    filter .6s ease;
}

.portrait-frame:hover .portrait-image img {
  transform: scale(1.09);
  filter:
    saturate(.92)
    contrast(1.08)
    brightness(.95);
}

/* =========================================
   CINEMATIC OVERLAY
========================================= */

.portrait-overlay {
  position: absolute;
  inset: 0;
  pointer-events: none;

  background:
    linear-gradient(
      to bottom,
      rgba(0,0,0,.05) 20%,
      rgba(0,0,0,.08) 40%,
      rgba(0,0,0,.72) 100%
    );

  z-index: 1;
}

/* subtle gold glow */

.portrait-overlay::after {
  content: '';
  position: absolute;
  inset: 0;

  background:
    radial-gradient(
      circle at 70% 20%,
      rgba(200,167,106,.18),
      transparent 35%
    );

  mix-blend-mode: screen;
}

/* =========================================
   BOTTOM INFORMATION
========================================= */

.portrait-caption {
  position: absolute;
  left: 25px;
  right: 25px;
  bottom: 25px;

  display: flex;
  align-items: flex-end;
  gap: 13px;

  z-index: 3;
}

.portrait-line {
  width: 1px;
  height: 55px;
  background: var(--gold);
  flex-shrink: 0;
}

.portrait-caption small {
  display: block;

  color: var(--gold-light);

  font-size: 7px;
  letter-spacing: 2.5px;
  line-height: 1.5;

  margin-bottom: 7px;
}

.portrait-caption strong {
  display: block;

  color: white;

  font-family: 'Playfair Display', serif;
  font-size: 25px;
  line-height: .95;
  font-weight: 500;
  letter-spacing: -.5px;
}

/* =========================================
   FLOATING BADGE
========================================= */

.portrait-badge {
  position: absolute;

  top: 25px;
  right: -30px;

  width: 86px;
  height: 86px;

  border-radius: 50%;

  background: rgba(11,13,12,.9);
  border: 1px solid rgba(200,167,106,.55);

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  z-index: 4;

  box-shadow:
    0 15px 40px rgba(0,0,0,.35);

  transform: rotate(8deg);

  transition: .5s cubic-bezier(.2,.8,.2,1);
}

.portrait-frame:hover .portrait-badge {
  transform: rotate(0deg) scale(1.06);
}

.portrait-badge::before {
  content: '';
  position: absolute;
  inset: 5px;
  border: 1px dashed rgba(200,167,106,.3);
  border-radius: 50%;
}

.portrait-badge span {
  color: var(--gold);

  font-size: 6px;
  letter-spacing: 2px;
  font-weight: 700;
}

.portrait-badge b {
  color: white;

  font-family: 'Playfair Display', serif;

  font-size: 15px;
  font-weight: 500;

  margin-top: 3px;
}

/* =========================================
   DECORATIVE CORNERS
========================================= */

.portrait-corner {
  position: absolute;
  width: 38px;
  height: 38px;

  pointer-events: none;
}

.portrait-corner.top-left {
  top: -15px;
  left: -15px;

  border-top: 1px solid var(--gold);
  border-left: 1px solid var(--gold);
}

.portrait-corner.bottom-right {
  bottom: -15px;
  right: -15px;

  border-bottom: 1px solid var(--gold);
  border-right: 1px solid var(--gold);
}

/* =========================================
   MOBILE
========================================= */

@media (max-width: 650px) {

  .portrait-frame {
    width: 82%;
  }

  .portrait-caption {
    left: 18px;
    right: 18px;
    bottom: 18px;
  }

  .portrait-caption strong {
    font-size: 21px;
  }

  .portrait-caption small {
    font-size: 6px;
    letter-spacing: 2px;
  }

  .portrait-badge {
    width: 70px;
    height: 70px;
    right: -20px;
    top: 20px;
  }

  .portrait-badge b {
    font-size: 12px;
  }

  .portrait-corner {
    width: 28px;
    height: 28px;
  }
}
/* MARQUEE */

.marquee {
  overflow: hidden;
  background: var(--gold);
  color: #10120f;
  padding: 15px 0;
}

.marquee-track {
  width: max-content;
  display: flex;
  align-items: center;
  gap: 35px;
  animation: marquee 25s linear infinite;
}

.marquee span {
  font-size: 9px;
  font-weight: 800;
  letter-spacing: 3px;
  white-space: nowrap;
}

.marquee b {
  font-size: 10px;
}

@keyframes marquee {
  to { transform: translateX(-50%); }
}

/* GENERAL */

.section {
  padding: 120px 8vw;
}

.section-label {
  margin-bottom: 28px;
}

.section-label.light {
  color: var(--gold-light);
}

h2 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(48px, 5vw, 76px);
  line-height: .98;
  letter-spacing: -3px;
  font-weight: 500;
}

h2 span {
  color: #9b9f98;
  font-style: italic;
}

/* ABOUT */

.about-section {
  background: var(--cream);
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr .8fr;
  gap: 12vw;
}

.about-text {
  padding-top: 10px;
}

.about-text p {
  color: #626660;
  line-height: 1.8;
  font-size: 14px;
  margin-bottom: 22px;
}

.about-text p.large {
  font-family: 'Playfair Display', serif;
  color: var(--black);
  font-size: 24px;
  line-height: 1.4;
}

.outline-btn {
  background: transparent;
  border: 1px solid rgba(12,14,12,.25);
  padding: 14px 18px;
  display: inline-flex;
  align-items: center;
  gap: 22px;
  font-size: 10px;
  letter-spacing: 1px;
  transition: .3s;
}

.outline-btn:hover {
  background: var(--black);
  color: white;
}

.expanded-story {
  border-left: 1px solid var(--gold);
  padding-left: 20px;
  margin-top: 25px;
}

/* WEALTH */

.wealth-section {
  position: relative;
  background: var(--black);
  color: white;
  overflow: hidden;
}

.wealth-bg {
  position: absolute;
  width: 600px;
  height: 600px;
  border-radius: 50%;
  border: 1px solid rgba(200,167,106,.08);
  right: -200px;
  top: -150px;
}

.wealth-bg:before,
.wealth-bg:after {
  content: '';
  position: absolute;
  border: 1px solid rgba(200,167,106,.06);
  border-radius: 50%;
  inset: 70px;
}

.wealth-bg:after {
  inset: 150px;
}

.section-heading {
  display: grid;
  grid-template-columns: 1fr .55fr;
  gap: 10vw;
  margin-bottom: 65px;
  position: relative;
}

.section-heading > p {
  align-self: end;
  color: #8d928b;
  font-size: 14px;
  line-height: 1.8;
  max-width: 400px;
}

.pillar-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  background: rgba(255,255,255,.12);
  position: relative;
}

.pillar {
  min-height: 400px;
  background: var(--black);
  padding: 35px;
  display: flex;
  flex-direction: column;
  transition: .4s;
  position: relative;
}

.pillar:hover,
.pillar.active {
  background: #151916;
}

.pillar-number {
  color: #555b55;
  font-size: 9px;
  letter-spacing: 2px;
}

.pillar-icon {
  width: 38px;
  height: 38px;
  color: var(--gold);
  margin: 65px 0 25px;
}

.pillar-icon svg {
  width: 100%;
  height: 100%;
}

.pillar h3 {
  font-family: 'Playfair Display', serif;
  font-size: 30px;
  font-weight: 500;
}

.pillar p {
  color: #858b84;
  font-size: 12px;
  line-height: 1.7;
  margin-top: 13px;
  max-width: 300px;
}

.pillar-footer {
  margin-top: auto;
  padding-top: 30px;
  border-top: 1px solid rgba(255,255,255,.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.pillar-footer span {
  color: var(--gold);
  font-size: 7px;
  letter-spacing: 2px;
}

.pillar-footer button {
  border: none;
  background: none;
  color: white;
  font-size: 10px;
  display: flex;
  gap: 8px;
}

/* STRATEGY */

.strategy-section {
  background: #e9e4da;
}

.strategy-heading {
  display: grid;
  grid-template-columns: 1fr .55fr;
  gap: 10vw;
  margin-bottom: 55px;
}

.strategy-heading p {
  color: #686c65;
  font-size: 14px;
  line-height: 1.8;
  align-self: end;
}

.strategy-container {
  display: grid;
  grid-template-columns: .9fr 1.1fr;
  gap: 1px;
  background: var(--dark-line);
  border: 1px solid var(--dark-line);
}

.strategy-options {
  background: #eeeae1;
}

.strategy-options button {
  width: 100%;
  border: none;
  border-bottom: 1px solid var(--dark-line);
  background: transparent;
  padding: 22px;
  text-align: left;
  display: flex;
  align-items: center;
  gap: 16px;
  transition: .3s;
}

.strategy-options button:last-child {
  border-bottom: none;
}

.strategy-options button:hover,
.strategy-options button.selected {
  background: var(--black);
  color: white;
}

.strategy-option-icon {
  width: 42px;
  height: 42px;
  display: grid;
  place-items: center;
  border: 1px solid currentColor;
  font-size: 10px;
}

.strategy-options small {
  display: block;
  font-size: 7px;
  letter-spacing: 2px;
  color: #999;
  margin-bottom: 5px;
}

.strategy-options strong {
  font-size: 12px;
}

.strategy-options .arrow {
  margin-left: auto;
  opacity: .5;
}

.strategy-result {
  background: var(--black);
  color: white;
  min-height: 480px;
  padding: 35px;
  position: relative;
}

.result-top {
  display: flex;
  justify-content: space-between;
  font-size: 8px;
  letter-spacing: 2px;
  color: #747973;
}

.result-dot {
  width: 6px;
  height: 6px;
  background: var(--gold);
  border-radius: 50%;
}

.result-content {
  max-width: 500px;
  margin: 75px auto 0;
}

.result-icon {
  color: var(--gold);
  font-family: 'Playfair Display', serif;
  font-size: 25px;
}

.result-content h3 {
  font-family: 'Playfair Display', serif;
  font-size: 42px;
  font-weight: 500;
  margin: 12px 0;
}

.result-content > p {
  color: #888e87;
  line-height: 1.7;
  font-size: 13px;
}

.result-path {
  display: flex;
  gap: 8px;
  margin: 30px 0;
}

.path-step {
  flex: 1;
  padding: 12px;
  border: 1px solid rgba(255,255,255,.1);
  color: #9a9e98;
  font-size: 9px;
  line-height: 1.5;
}

.path-step span {
  display: block;
  color: var(--gold);
  margin-bottom: 8px;
}

.dark-btn {
  background: white;
  color: var(--black);
}

/* REAL ESTATE */

.real-estate-section {
  background: var(--cream);
}

.real-estate-top {
  display: grid;
  grid-template-columns: 1fr .55fr;
  gap: 10vw;
  margin-bottom: 65px;
}

.real-estate-copy {
  align-self: end;
}

.real-estate-copy p {
  color: #656963;
  font-size: 14px;
  line-height: 1.8;
  margin-bottom: 22px;
}

.property-showcase {
  display: grid;
  grid-template-columns: 1fr 1.3fr 1fr;
  gap: 12px;
}

.property-image {
  height: 530px;
  position: relative;
  overflow: hidden;
  background: #353a35;
  transition: .5s;
}

.property:hover .property-image {
  transform: translateY(-7px);
}

.property-0 {
  background:
    linear-gradient(135deg, rgba(0,0,0,.1), rgba(0,0,0,.7)),
    linear-gradient(145deg, #9b8f7b, #363832 55%, #1a1d1a);
}

.property-1 {
  height: 620px;
  margin-top: -45px;
  background:
    linear-gradient(135deg, rgba(0,0,0,.1), rgba(0,0,0,.7)),
    linear-gradient(145deg, #b5a383, #505248 45%, #1a1d1a);
}

.property-2 {
  background:
    linear-gradient(135deg, rgba(0,0,0,.1), rgba(0,0,0,.7)),
    linear-gradient(145deg, #777d71, #353933 55%, #151815);
}

.property-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(transparent 40%, rgba(0,0,0,.75));
}

.property-type {
  position: absolute;
  top: 20px;
  left: 20px;
  color: white;
  border: 1px solid rgba(255,255,255,.3);
  padding: 7px 10px;
  font-size: 7px;
  letter-spacing: 2px;
}

.property-expand {
  position: absolute;
  top: 20px;
  right: 20px;
  width: 38px;
  height: 38px;
  border-radius: 50%;
  border: 1px solid rgba(255,255,255,.3);
  background: rgba(0,0,0,.15);
  color: white;
  backdrop-filter: blur(10px);
}

.property-bottom {
  position: absolute;
  left: 25px;
  bottom: 25px;
  color: white;
}

.property-bottom small {
  display: block;
  color: var(--gold-light);
  font-size: 7px;
  letter-spacing: 2px;
  margin-bottom: 8px;
}

.property-bottom strong {
  font-family: 'Playfair Display', serif;
  font-size: 27px;
  font-weight: 500;
}

.property-meta {
  padding: 13px 3px;
  display: flex;
  justify-content: space-between;
  font-size: 8px;
  letter-spacing: 1px;
  color: #777b74;
}

/* EDUCATION */

.education-section {
  background: #151815;
  color: white;
}

.education-heading {
  grid-template-columns: 1fr .55fr;
}

.education-heading h2 {
  color: white;
}

.education-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1px;
  background: rgba(255,255,255,.1);
}

.education-card {
  background: #151815;
  min-height: 350px;
  padding: 28px;
  cursor: pointer;
  transition: .35s;
  position: relative;
}

.education-card:hover {
  background: #202520;
  transform: translateY(-5px);
}

.education-top {
  display: flex;
  justify-content: space-between;
  color: var(--gold);
  font-size: 7px;
  letter-spacing: 2px;
}

.education-arrow {
  font-size: 16px;
}

.education-icon {
  width: 38px;
  height: 38px;
  color: var(--gold);
  margin-top: 65px;
}

.education-icon svg {
  width: 100%;
  height: 100%;
}

.education-card h3 {
  font-family: 'Playfair Display', serif;
  font-size: 25px;
  font-weight: 500;
  margin-top: 20px;
}

.education-card p {
  color: #858b84;
  font-size: 11px;
  line-height: 1.7;
  margin-top: 10px;
}

.education-link {
  position: absolute;
  bottom: 28px;
  left: 28px;
  right: 28px;
  padding-top: 15px;
  border-top: 1px solid rgba(255,255,255,.1);
  display: flex;
  justify-content: space-between;
  color: #a8aca7;
  font-size: 9px;
}

/* NUMBERS */

.numbers-section {
  background: var(--gold);
  color: var(--black);
  padding: 55px 8vw;
}

.numbers-grid {
  max-width: 1300px;
  margin: auto;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

.stat {
  padding: 0 35px;
  border-right: 1px solid rgba(0,0,0,.2);
}

.stat:first-child {
  padding-left: 0;
}

.stat:last-child {
  border: none;
}

.stat strong {
  display: block;
  font-family: 'Playfair Display', serif;
  font-size: 48px;
  font-weight: 500;
}

.stat span {
  font-size: 8px;
  letter-spacing: 2px;
  text-transform: uppercase;
}

/* TESTIMONIALS */

.testimonials-section {
  background: var(--cream);
}

.testimonial-layout {
  display: grid;
  grid-template-columns: .8fr 1.2fr;
  gap: 12vw;
  align-items: center;
}

.testimonial-intro h2 {
  font-size: clamp(42px, 4vw, 62px);
}

.testimonial-controls {
  display: flex;
  align-items: center;
  gap: 18px;
  margin-top: 60px;
}

.testimonial-controls button {
  width: 42px;
  height: 42px;
  border: 1px solid var(--dark-line);
  background: transparent;
}

.testimonial-controls span {
  font-size: 8px;
  letter-spacing: 2px;
  color: #777;
}

.testimonial-card {
  background: var(--black);
  color: white;
  padding: 60px;
  min-height: 400px;
  position: relative;
}

.quote-mark {
  color: var(--gold);
  font-family: 'Playfair Display', serif;
  font-size: 80px;
  line-height: .5;
}

.quote {
  font-family: 'Playfair Display', serif;
  font-size: 27px;
  line-height: 1.45;
  margin: 35px 0 45px;
}

.testimonial-person {
  display: flex;
  align-items: center;
  gap: 13px;
}

.avatar {
  width: 38px;
  height: 38px;
  border-radius: 50%;
  display: grid;
  place-items: center;
  border: 1px solid var(--gold);
  color: var(--gold);
  font-size: 9px;
}

.testimonial-person strong {
  display: block;
  font-size: 11px;
}

.testimonial-person span {
  display: block;
  font-size: 8px;
  color: #777;
  margin-top: 3px;
}

/* SPEAKING */

.speaking-section {
  position: relative;
  background: var(--black);
  color: white;
  padding: 130px 8vw;
  display: grid;
  grid-template-columns: 1fr .6fr;
  gap: 12vw;
  overflow: hidden;
}

.speaking-grid {
  position: absolute;
  inset: 0;
  opacity: .15;
  background-image:
    linear-gradient(rgba(255,255,255,.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,.05) 1px, transparent 1px);
  background-size: 80px 80px;
}

.speaking-content,
.speaking-side {
  position: relative;
  z-index: 1;
}

.speaking-content h2 {
  font-size: clamp(55px, 6vw, 90px);
  margin-bottom: 30px;
}

.speaking-content h2 em {
  color: var(--gold-light);
  font-weight: 500;
}

.speaking-content > p {
  max-width: 480px;
  color: #858a84;
  line-height: 1.8;
  font-size: 13px;
  margin-bottom: 30px;
}

.light-btn {
  color: #111;
}

.speaking-side {
  display: flex;
  align-items: center;
}

.event-card {
  width: 100%;
  border: 1px solid rgba(255,255,255,.12);
  padding: 30px;
}

.event-card > span {
  color: var(--gold);
  font-size: 8px;
  letter-spacing: 3px;
}

.event-card div {
  margin-top: 35px;
}

.event-card strong {
  display: block;
  font-family: 'Playfair Display', serif;
  font-size: 25px;
  font-weight: 500;
  padding: 14px 0;
  border-bottom: 1px solid rgba(255,255,255,.1);
}

/* FINAL CTA */

.final-cta {
  background: var(--cream);
  text-align: center;
  padding: 150px 8vw;
  position: relative;
  overflow: hidden;
}

.final-cta .section-label {
  position: relative;
}

.final-cta h2 {
  position: relative;
  font-size: clamp(60px, 7vw, 105px);
  margin-bottom: 30px;
}

.final-cta h2 span {
  color: var(--gold);
}

.final-cta p {
  max-width: 480px;
  margin: auto;
  color: #6d716a;
  line-height: 1.7;
  font-size: 13px;
  position: relative;
}

.cta-buttons {
  position: relative;
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-top: 35px;
}

.cta-circle {
  position: absolute;
  border: 1px solid rgba(200,167,106,.2);
  border-radius: 50%;
  pointer-events: none;
}

.circle-one {
  width: 500px;
  height: 500px;
  left: -200px;
  top: -100px;
}

.circle-two {
  width: 350px;
  height: 350px;
  right: -100px;
  bottom: -100px;
}

/* FOOTER */

footer {
  background: var(--black);
  color: white;
  padding: 70px 8vw 25px;
}

.footer-main {
  display: flex;
  justify-content: space-between;
  padding-bottom: 65px;
}

.footer-brand p {
  color: #6f746e;
  font-size: 10px;
  margin-top: 20px;
}

.footer-links {
  display: flex;
  gap: 100px;
}

.footer-links div {
  display: flex;
  flex-direction: column;
  gap: 13px;
}

.footer-links span {
  color: var(--gold);
  font-size: 7px;
  letter-spacing: 2px;
  margin-bottom: 5px;
}

.footer-links a {
  color: #898e88;
  text-decoration: none;
  font-size: 10px;
}

.footer-links a:hover {
  color: white;
}

.footer-bottom {
  border-top: 1px solid rgba(255,255,255,.1);
  padding-top: 20px;
  display: flex;
  justify-content: space-between;
  color: #555a54;
  font-size: 8px;
  letter-spacing: .5px;
}

/* MODALS */

.modal-backdrop {
  position: fixed;
  z-index: 500;
  inset: 0;
  background: rgba(0,0,0,.72);
  backdrop-filter: blur(12px);
  display: grid;
  place-items: center;
  padding: 25px;
}

.modal {
  width: min(650px, 100%);
  max-height: 90vh;
  overflow-y: auto;
  background: var(--cream);
  color: var(--black);
  padding: 50px;
  position: relative;
  box-shadow: 0 40px 100px rgba(0,0,0,.4);
}

.modal-close {
  position: absolute;
  top: 18px;
  right: 18px;
  width: 35px;
  height: 35px;
  border: 1px solid var(--dark-line);
  background: transparent;
  font-size: 22px;
}

.modal h2 {
  font-size: 52px;
  margin-bottom: 35px;
}

.contact-options {
  display: grid;
  gap: 8px;
}

.contact-options button {
  width: 100%;
  padding: 17px;
  border: 1px solid var(--dark-line);
  background: transparent;
  display: flex;
  align-items: center;
  gap: 14px;
  text-align: left;
  transition: .25s;
}

.contact-options button:hover,
.contact-options button.selected {
  background: var(--black);
  color: white;
}

.contact-options button > span {
  width: 38px;
  height: 38px;
  display: grid;
  place-items: center;
  border: 1px solid currentColor;
  color: var(--gold);
}

.contact-options strong {
  display: block;
  font-size: 11px;
}

.contact-options small {
  display: block;
  color: #777;
  margin-top: 4px;
  font-size: 8px;
}

.contact-options b {
  margin-left: auto;
  font-weight: 400;
}

.full-btn {
  width: 100%;
  justify-content: center;
  margin-top: 15px;
}

.full-btn:disabled {
  opacity: .4;
  cursor: not-allowed;
}

.success-message {
  color: #626660;
  font-size: 11px;
  line-height: 1.6;
  margin-top: 15px;
}

.pillar-modal h2 {
  margin-top: 12px;
}

.pillar-icon.large {
  width: 50px;
  height: 50px;
  margin: 15px 0 30px;
}

.modal-description {
  color: #696d67;
  font-size: 13px;
  line-height: 1.8;
  margin-bottom: 25px;
}

.modal-list {
  border-top: 1px solid var(--dark-line);
  margin-bottom: 25px;
}

.modal-list div {
  padding: 13px 0;
  border-bottom: 1px solid var(--dark-line);
  font-size: 10px;
}

.modal-list span {
  color: var(--gold);
  margin-right: 10px;
}

.modal-property-image {
  height: 220px;
  margin-bottom: 30px;
}

.modal-property-image.property-0 {
  background: linear-gradient(145deg, #9b8f7b, #363832 55%, #1a1d1a);
}

.modal-property-image.property-1 {
  background: linear-gradient(145deg, #b5a383, #505248 45%, #1a1d1a);
}

.modal-property-image.property-2 {
  background: linear-gradient(145deg, #777d71, #353933 55%, #151815);
}

.modal-property-image span {
  display: inline-block;
  margin: 20px;
  padding: 7px 10px;
  color: white;
  border: 1px solid rgba(255,255,255,.3);
  font-size: 7px;
  letter-spacing: 2px;
}

.property-modal p {
  color: #686c66;
  font-size: 13px;
  line-height: 1.8;
  margin-bottom: 25px;
}

/* ANIMATION */

.reveal {
  animation: reveal .9s cubic-bezier(.2,.7,.2,1) both;
}

.delay-1 { animation-delay: .1s; }
.delay-2 { animation-delay: .2s; }
.delay-3 { animation-delay: .3s; }
.delay-4 { animation-delay: .4s; }

@keyframes reveal {
  from {
    opacity: 0;
    transform: translateY(25px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.modal-enter-active,
.modal-leave-active {
  transition: .3s ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}

.modal-enter-from .modal,
.modal-leave-to .modal {
  transform: translateY(20px) scale(.98);
}

/* RESPONSIVE */

@media (max-width: 1000px) {
  .desktop-nav {
    display: none;
  }

  .nav-cta {
    display: none;
  }

  .mobile-menu {
    display: block;
  }

  .mobile-nav {
    display: flex;
    flex-direction: column;
    gap: 20px;
    background: rgba(11,13,12,.97);
    padding: 25px 5vw;
    margin-top: 15px;
  }

  .mobile-nav a {
    color: white;
    text-decoration: none;
    font-size: 12px;
  }

  .mobile-nav button {
    border: none;
    background: var(--gold);
    padding: 14px;
    font-weight: 700;
  }

  .hero {
    grid-template-columns: 1fr;
    padding-top: 150px;
  }

  .hero-visual {
    min-height: 500px;
    margin-top: 60px;
  }

  .about-grid,
  .section-heading,
  .strategy-heading,
  .real-estate-top,
  .testimonial-layout,
  .speaking-section {
    grid-template-columns: 1fr;
    gap: 45px;
  }

  .pillar-grid {
    grid-template-columns: 1fr;
  }

  .pillar {
    min-height: 330px;
  }

  .property-showcase {
    grid-template-columns: 1fr;
  }

  .property-image,
  .property-1 {
    height: 480px;
    margin-top: 0;
  }

  .education-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .numbers-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 35px 0;
  }

  .stat:nth-child(2) {
    border: none;
  }

  .speaking-section {
    padding-top: 100px;
    padding-bottom: 100px;
  }
}

@media (max-width: 650px) {
  .nav {
    padding: 15px 5vw;
  }

  .hero {
    padding-left: 6vw;
    padding-right: 6vw;
  }

  .hero h1 {
    font-size: 58px;
    letter-spacing: -3px;
  }

  .hero-copy {
    font-size: 13px;
  }

  .hero-actions,
  .cta-buttons {
    flex-direction: column;
    align-items: stretch;
  }

  .primary-btn,
  .outline-btn {
    justify-content: center;
  }

  .hero-proof {
    gap: 15px;
  }

  .hero-proof strong {
    font-size: 22px;
  }

  .hero-proof span {
    font-size: 6px;
  }

  .hero-visual {
    min-height: 400px;
  }

  .portrait-frame {
    width: 80%;
  }

  .floating-card {
    transform: scale(.8);
  }

  .income-card {
    left: -7%;
  }

  .property-card {
    right: -7%;
  }

  .section {
    padding: 85px 6vw;
  }

  h2 {
    font-size: 47px;
    letter-spacing: -2px;
  }

  .strategy-container {
    grid-template-columns: 1fr;
  }

  .result-content {
    margin-top: 50px;
  }

  .result-content h3 {
    font-size: 34px;
  }

  .result-path {
    flex-direction: column;
  }

  .education-grid {
    grid-template-columns: 1fr;
  }

  .education-card {
    min-height: 300px;
  }

  .numbers-section {
    padding-left: 6vw;
    padding-right: 6vw;
  }

  .numbers-grid {
    grid-template-columns: 1fr 1fr;
  }

  .stat {
    padding: 0 15px;
  }

  .stat strong {
    font-size: 38px;
  }

  .stat span {
    font-size: 6px;
  }

  .testimonial-card {
    padding: 35px;
  }

  .quote {
    font-size: 22px;
  }

  .footer-main {
    flex-direction: column;
    gap: 50px;
  }

  .footer-links {
    gap: 50px;
  }

  .footer-bottom {
    flex-direction: column;
    gap: 10px;
  }

  .modal {
    padding: 35px 25px;
  }

  .modal h2 {
    font-size: 43px;
  }
}
</style>
```
