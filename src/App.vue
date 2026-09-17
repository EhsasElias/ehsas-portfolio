<script setup>
import { ref, computed } from 'vue'

const language = ref('en')
const isAr = computed(() => language.value === 'ar')

const content = {
  en: {
    nav: ['Home', 'Work', 'Services', 'About', 'Contact'],
    eyebrow: 'E-commerce developer • Salla • Zid • Automation',
    title: 'I build polished storefronts and the systems behind them.',
    subtitle: 'Portfolio demos focused on store setup, product operations, integrations, automation, and conversion-friendly UX.',
    primary: 'View selected work',
    secondary: 'Contact me',
    badge: 'Available for remote projects',
    stats: [
      ['4', 'Showcase projects'],
      ['AR / EN', 'Bilingual delivery'],
      ['Full-stack', 'Laravel + Vue']
    ],
    workTitle: 'Selected work',
    workSubtitle: 'Each project is presented transparently as a portfolio demo and built to demonstrate a different e-commerce skill set.',
    servicesTitle: 'What I can deliver',
    aboutTitle: 'Technical, but focused on the business result.',
    aboutText: 'I combine storefront implementation with backend thinking: product data, APIs, imports, automation, admin workflows, and responsive interfaces. The goal is not just a good-looking store — it is an easier store to operate.',
    contactTitle: 'Have a store or workflow to improve?',
    contactText: 'I can help with Salla / Zid setup, product operations, custom development, Laravel APIs, Vue interfaces, and automation.',
    contactBtn: 'Open GitHub profile'
  },
  ar: {
    nav: ['الرئيسية', 'الأعمال', 'الخدمات', 'عني', 'تواصل'],
    eyebrow: 'مطور تجارة إلكترونية • سلة • زد • أتمتة',
    title: 'أبني متاجر احترافية والأنظمة التي تعمل خلفها.',
    subtitle: 'نماذج أعمال تركز على تجهيز المتاجر، إدارة المنتجات، الربط، الأتمتة، وتجربة استخدام تساعد على البيع.',
    primary: 'شاهد الأعمال',
    secondary: 'تواصل معي',
    badge: 'متاح للمشاريع عن بُعد',
    stats: [
      ['4', 'مشاريع عرض'],
      ['AR / EN', 'دعم عربي وإنجليزي'],
      ['Full-stack', 'Laravel + Vue']
    ],
    workTitle: 'أعمال مختارة',
    workSubtitle: 'كل مشروع موضح بصدق على أنه نموذج Portfolio، وكل واحد يبرز مهارة مختلفة في التجارة الإلكترونية.',
    servicesTitle: 'ما الذي أستطيع تنفيذه',
    aboutTitle: 'تقني، لكن تركيزي على نتيجة العمل.',
    aboutText: 'أجمع بين تنفيذ واجهات المتاجر والتفكير في الخلفية: بيانات المنتجات، APIs، الاستيراد، الأتمتة، لوحات الإدارة، وتجربة الاستخدام المتجاوبة. الهدف ليس متجراً جميلاً فقط، بل متجراً أسهل في التشغيل.',
    contactTitle: 'عندك متجر أو عملية تريد تطويرها؟',
    contactText: 'أساعد في سلة وزد، تجهيز المنتجات، التطوير المخصص، Laravel APIs، واجهات Vue، والأتمتة.',
    contactBtn: 'افتح حساب GitHub'
  }
}

const projects = [
  {
    name: 'NOVA Perfumes',
    type: 'Salla Demo',
    descEn: 'Premium perfume storefront focused on merchandising, variants, campaigns, and mobile shopping UX.',
    descAr: 'متجر عطور تجريبي يركز على عرض المنتجات، الخيارات، الحملات، وتجربة الشراء على الجوال.',
    repo: 'https://github.com/EhsasElias/nova-perfumes-salla',
    tag: 'Salla'
  },
  {
    name: 'TechZone',
    type: 'Zid Demo',
    descEn: 'Electronics catalog demo built around structured product data, inventory thinking, filtering, and scale.',
    descAr: 'متجر إلكترونيات تجريبي يركز على تنظيم البيانات، المخزون، الفلاتر، والتوسع بعدد منتجات كبير.',
    repo: 'https://github.com/EhsasElias/techzone-zid',
    tag: 'Zid'
  },
  {
    name: 'Bean House',
    type: 'Salla Demo',
    descEn: 'Coffee and gifting storefront centered on bundles, seasonal merchandising, and visual storytelling.',
    descAr: 'متجر قهوة وهدايا يركز على الباقات، المواسم، والعرض البصري الاحترافي للمنتجات.',
    repo: 'https://github.com/EhsasElias/bean-house-salla',
    tag: 'Salla'
  },
  {
    name: 'Store Automation',
    type: 'Dashboard',
    descEn: 'Operations dashboard concept for validating, preparing, and automating product workflows.',
    descAr: 'لوحة عمليات لتجهيز بيانات المنتجات والتحقق منها وأتمتة سير العمل.',
    repo: 'https://github.com/EhsasElias/store-automation-dashboard',
    tag: 'Automation'
  }
]

const services = [
  ['Store setup', 'Salla / Zid configuration, categories, product structure, shipping and payment readiness'],
  ['Product operations', 'Bulk product preparation, Excel workflows, variants, SKUs and catalog organization'],
  ['Custom development', 'Laravel APIs, Vue interfaces, dashboards and integrations'],
  ['Automation', 'Reduce repetitive store operations with validation, imports and workflow tooling']
]

const t = computed(() => content[language.value])
</script>

<template>
  <div class="site" :dir="isAr ? 'rtl' : 'ltr'">
    <header class="nav shell">
      <a class="brand" href="#home" aria-label="Ehsas home">
        <span class="brand-mark">E</span>
        <span>Ehsas</span>
      </a>

      <nav class="nav-links">
        <a href="#home">{{ t.nav[0] }}</a>
        <a href="#work">{{ t.nav[1] }}</a>
        <a href="#services">{{ t.nav[2] }}</a>
        <a href="#about">{{ t.nav[3] }}</a>
        <a href="#contact">{{ t.nav[4] }}</a>
      </nav>

      <button class="lang" @click="language = isAr ? 'en' : 'ar'">
        {{ isAr ? 'EN' : 'العربية' }}
      </button>
    </header>

    <main>
      <section id="home" class="hero shell">
        <div class="hero-copy">
          <div class="availability"><span></span>{{ t.badge }}</div>
          <p class="eyebrow">{{ t.eyebrow }}</p>
          <h1>{{ t.title }}</h1>
          <p class="hero-text">{{ t.subtitle }}</p>
          <div class="actions">
            <a class="btn primary" href="#work">{{ t.primary }}</a>
            <a class="btn secondary" href="#contact">{{ t.secondary }}</a>
          </div>
        </div>

        <aside class="hero-card">
          <div class="terminal-head">
            <span></span><span></span><span></span>
            <small>portfolio.config</small>
          </div>
          <div class="terminal-body" dir="ltr">
            <p><b>focus</b>: ecommerce</p>
            <p><b>platforms</b>: ['Salla', 'Zid']</p>
            <p><b>backend</b>: 'Laravel'</p>
            <p><b>frontend</b>: 'Vue'</p>
            <p><b>automation</b>: true</p>
            <p><b>languages</b>: ['AR', 'EN']</p>
          </div>
        </aside>
      </section>

      <section class="stats shell">
        <article v-for="stat in t.stats" :key="stat[1]">
          <strong>{{ stat[0] }}</strong>
          <span>{{ stat[1] }}</span>
        </article>
      </section>

      <section id="work" class="section shell">
        <div class="section-heading">
          <p class="eyebrow">Portfolio</p>
          <h2>{{ t.workTitle }}</h2>
          <p>{{ t.workSubtitle }}</p>
        </div>

        <div class="projects">
          <a v-for="project in projects" :key="project.name" class="project" :href="project.repo" target="_blank" rel="noreferrer">
            <div class="project-top">
              <span class="pill">{{ project.tag }}</span>
              <span class="arrow">↗</span>
            </div>
            <div>
              <small>{{ project.type }}</small>
              <h3>{{ project.name }}</h3>
              <p>{{ isAr ? project.descAr : project.descEn }}</p>
            </div>
          </a>
        </div>
      </section>

      <section id="services" class="section shell">
        <div class="section-heading compact">
          <p class="eyebrow">Capabilities</p>
          <h2>{{ t.servicesTitle }}</h2>
        </div>
        <div class="service-grid">
          <article v-for="(service, index) in services" :key="service[0]">
            <span>0{{ index + 1 }}</span>
            <h3>{{ service[0] }}</h3>
            <p>{{ service[1] }}</p>
          </article>
        </div>
      </section>

      <section id="about" class="about shell">
        <div>
          <p class="eyebrow">Approach</p>
          <h2>{{ t.aboutTitle }}</h2>
        </div>
        <p>{{ t.aboutText }}</p>
      </section>

      <section id="contact" class="contact shell">
        <div>
          <p class="eyebrow">Contact</p>
          <h2>{{ t.contactTitle }}</h2>
          <p>{{ t.contactText }}</p>
        </div>
        <a class="btn light" href="https://github.com/EhsasElias" target="_blank" rel="noreferrer">{{ t.contactBtn }} ↗</a>
      </section>
    </main>

    <footer class="shell footer">
      <span>© 2026 Ehsas</span>
      <span>Built with Vue + Vite</span>
    </footer>
  </div>
</template>
