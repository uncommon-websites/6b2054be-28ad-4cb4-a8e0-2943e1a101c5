<script>
  export let mobileMenuOpen = false;
</script>

<header class="fixed top-0 left-0 right-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center h-16">
      <!-- Logo -->
      <div class="flex-shrink-0 flex items-center gap-2 cursor-pointer">
        <div class="w-8 h-8 bg-gray-900 rounded-full flex items-center justify-center text-white">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M18 10c0 3.866-3.582 7-8 7a8.841 8.841 0 01-4.083-.98L2 17l1.338-3.123C2.493 12.767 2 11.434 2 10c0-3.866 3.582-7 8-7s8 3.134 8 7zM7 9H5v2h2V9zm8 0h-2v2h2V9zM9 9h2v2H9V9z" clip-rule="evenodd" />
          </svg>
        </div>
        <span class="font-bold text-xl tracking-tight">Delphi</span>
      </div>

      <!-- Desktop Navigation -->
      <nav class="hidden md:flex space-x-8">
        <a href="#pricing" class="text-sm font-medium text-gray-600 hover:text-gray-900">Pricing</a>
        <a href="#voices" class="text-sm font-medium text-gray-600 hover:text-gray-900">Voice Samples</a>
        <a href="#blog" class="text-sm font-medium text-gray-600 hover:text-gray-900">Blog</a>
        <a href="#experts" class="text-sm font-medium text-gray-600 hover:text-gray-900">Experts</a>
      </nav>

      <!-- CTA Button -->
      <div class="hidden md:flex items-center">
        <a href="#signin" class="inline-flex items-center px-4 py-2 border border-transparent text-sm font-medium rounded-full text-white bg-gray-900 hover:bg-gray-800 transition-colors">
          Sign In
          <svg class="ml-2 -mr-1 w-4 h-4 text-gray-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-8.707l-3-3a1 1 0 00-1.414 1.414L10.586 9H7a1 1 0 100 2h3.586l-1.293 1.293a1 1 0 101.414 1.414l3-3a1 1 0 000-1.414z" clip-rule="evenodd" />
          </svg>
        </a>
      </div>

      <!-- Mobile menu button -->
      <div class="md:hidden flex items-center">
        <button on:click={() => mobileMenuOpen = !mobileMenuOpen} class="text-gray-500 hover:text-gray-900 focus:outline-none" aria-label="Toggle mobile menu">
          <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
      </div>
    </div>
  </div>

  <!-- Mobile Menu -->
  {#if mobileMenuOpen}
    <div class="md:hidden bg-white border-b border-gray-100">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <a href="#pricing" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Pricing</a>
        <a href="#voices" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Voice Samples</a>
        <a href="#blog" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Blog</a>
        <a href="#experts" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Experts</a>
        <a href="#signin" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Sign In</a>
      </div>
    </div>
  {/if}
</header>
