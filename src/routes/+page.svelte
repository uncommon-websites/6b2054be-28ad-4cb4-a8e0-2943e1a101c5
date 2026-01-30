<script>
  import Header from '$lib/components/Header.svelte';
  import Hero from '$lib/components/Hero.svelte';
  import StatsGrid from '$lib/components/StatsGrid.svelte';
  import FeatureSection from '$lib/components/FeatureSection.svelte';
  import IntegrationSection from '$lib/components/IntegrationSection.svelte';
  import EngagementSection from '$lib/components/EngagementSection.svelte';
  import ComparisonTable from '$lib/components/ComparisonTable.svelte';
  import StepsSection from '$lib/components/StepsSection.svelte';
  import PricingSection from '$lib/components/PricingSection.svelte';
  import TeamSection from '$lib/components/TeamSection.svelte';
  import CTASection from '$lib/components/CTASection.svelte';
  import FAQSection from '$lib/components/FAQSection.svelte';
  import Footer from '$lib/components/Footer.svelte';

  const conversationalFeatures = [
    {
      title: "Voice & video chat",
      description: "Your clone speaks in your authentic voice across all channels",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z"/></svg>`,
      iconColor: "text-purple-500",
      iconBg: "bg-purple-50"
    },
    {
      title: "Instant training",
      description: "Upload YouTube, podcasts, articles—clone learns automatically",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>`,
      iconColor: "text-blue-500",
      iconBg: "bg-blue-50"
    },
    {
      title: "Authentic responses",
      description: "Only speaks your words, never improvises without consent",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/></svg>`,
      iconColor: "text-green-500",
      iconBg: "bg-green-50"
    },
    {
      title: "Unlimited conversations",
      description: "Answer infinite questions simultaneously, 24/7 availability",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z"/></svg>`,
      iconColor: "text-orange-500",
      iconBg: "bg-orange-50"
    },
    {
      title: "Personalized advice",
      description: "Each conversation is tailored to the individual's context",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"/></svg>`,
      iconColor: "text-pink-500",
      iconBg: "bg-pink-50"
    },
    {
      title: "Context retention",
      description: "Remembers past conversations for deeper relationships",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01"/></svg>`,
      iconColor: "text-indigo-500",
      iconBg: "bg-indigo-50"
    },
    {
      title: "Multi-channel access",
      description: "SMS, WhatsApp, Slack, website—meet users where they are",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z"/></svg>`,
      iconColor: "text-teal-500",
      iconBg: "bg-teal-50"
    },
    {
      title: "Privacy-first design",
      description: "Fully encrypted, never shared—your mind is yours forever",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"/></svg>`,
      iconColor: "text-red-500",
      iconBg: "bg-red-50"
    }
  ];

  const scalingFeatures = [
    {
      title: "40+ languages",
      description: "Reach global audiences in their native language automatically",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>`,
      iconColor: "text-blue-500",
      iconBg: "bg-blue-50"
    },
    {
      title: "Website embedding",
      description: "Add your clone to any website with one line of code",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/></svg>`,
      iconColor: "text-purple-500",
      iconBg: "bg-purple-50"
    },
    {
      title: "Contact collection",
      description: "Build your audience as people interact with your clone",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/></svg>`,
      iconColor: "text-green-500",
      iconBg: "bg-green-50"
    },
    {
      title: "CRM syncing",
      description: "Automatically sync contacts to your existing CRM system",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15"/></svg>`,
      iconColor: "text-orange-500",
      iconBg: "bg-orange-50"
    }
  ];

  const monetizationFeatures = [
    {
      title: "Analytics dashboard",
      description: "Track conversations, popular topics, and engagement metrics",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/></svg>`,
      iconColor: "text-blue-500",
      iconBg: "bg-blue-50"
    },
    {
      title: "Custom branding",
      description: "Match your clone's interface to your brand identity",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01"/></svg>`,
      iconColor: "text-purple-500",
      iconBg: "bg-purple-50"
    },
    {
      title: "Monetization tools",
      description: "Charge for access and create scalable revenue streams",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>`,
      iconColor: "text-green-500",
      iconBg: "bg-green-50"
    },
    {
      title: "API access",
      description: "Build custom applications powered by your digital clone",
      icon: `<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l3 3-3 3m5 0h3M5 20h14a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>`,
      iconColor: "text-orange-500",
      iconBg: "bg-orange-50"
    }
  ];
</script>

<Header />

<main>
  <Hero />
  <StatsGrid />
  
  <div id="product">
    <FeatureSection 
      tag="Conversational AI Platform" 
      tagColor="text-purple-500"
      headline="Your digital clone speaks in your authentic voice"
      description="Create an interactive AI clone trained on your content that answers questions exactly as you would. Voice, video, chat—your clone provides personalized advice at infinite scale while maintaining your unique perspective and wisdom."
      features={conversationalFeatures}
    >
      <div slot="image">
        <img src="/generated/image-a-professional-coach-or-expert-having-a--1769785694280-0.webp" alt="Expert having authentic video conversation" class="w-full h-auto" />
      </div>
    </FeatureSection>

    <FeatureSection 
      tag="Global Scale & Reach" 
      tagColor="text-blue-500"
      headline="Reach millions in their native language"
      description="Your clone speaks 40+ languages automatically, breaking down barriers and democratizing access to your wisdom. From website embedding to SMS integration, meet your audience wherever they are, 24/7."
      features={scalingFeatures}
      quote="Matthew Hussey, Relationship Expert: 'It has completely changed the game in terms of people having on-demand access to my mind.'"
    >
      <div slot="image">
        <img src="/generated/image-a-diverse-group-of-people-from-different-1769785699528-1.webp" alt="Global multilingual communication" class="w-full h-auto" />
      </div>
    </FeatureSection>

    <FeatureSection 
      tag="Analytics & Monetization" 
      tagColor="text-green-500"
      headline="Turn your expertise into scalable revenue"
      description="Track engagement, understand your audience, and monetize your knowledge. From analytics dashboards to custom branding and API access, Delphi gives you the tools to build a sustainable knowledge business."
      features={monetizationFeatures}
    >
      <div slot="image">
        <img src="/generated/image-a-successful-business-professional-revie-1769785702230-2.webp" alt="Professional reviewing analytics dashboard" class="w-full h-auto" />
      </div>
    </FeatureSection>
  </div>

  <IntegrationSection />
  <EngagementSection />
  <ComparisonTable />
  <StepsSection />
  <PricingSection />
  <TeamSection />
  <CTASection />
  <FAQSection />
</main>

<Footer />

