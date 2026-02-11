<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.tailwindcss.com"></script>
    <title>Modern Landing Page</title>
    <style>
        body { background-color: #0f172a; } /* Deep dark blue/black background */
    </style>
</head>
<body class="text-slate-200 font-sans">

  <nav class="flex items-center justify-between px-10 py-6 max-w-7xl mx-auto">
        <div class="text-2xl font-bold tracking-tighter text-white">LOGO</div>
        <div class="hidden md:flex space-x-8 text-sm font-medium">
            <a href="#" class="hover:text-blue-400 transition">Product</a>
            <a href="#" class="hover:text-blue-400 transition">Features</a>
            <a href="#" class="hover:text-blue-400 transition">Pricing</a>
        </div>
        <button class="bg-blue-600 hover:bg-blue-500 text-white px-5 py-2 rounded-full text-sm font-semibold transition">
            Get Started
        </button>
    </nav>

  <section class="max-w-4xl mx-auto text-center pt-20 pb-16 px-6">
        <h1 class="text-5xl md:text-7xl font-extrabold text-white leading-tight mb-6">
            Build your next idea <span class="text-blue-500">faster than ever.</span>
        </h1>
        <p class="text-lg text-slate-400 mb-10 max-w-2xl mx-auto">
            Stop worrying about boilerplate. Our platform handles the heavy lifting so you can focus on shipping features that your users actually love.
        </p>
        <div class="flex flex-col sm:flex-row justify-center gap-4">
            <button class="bg-white text-slate-900 px-8 py-3 rounded-lg font-bold hover:bg-slate-200 transition">
                Start for free
            </button>
            <button class="border border-slate-700 px-8 py-3 rounded-lg font-bold hover:bg-slate-800 transition">
                View Documentation
            </button>
        </div>
    </section>

  <section class="max-w-7xl mx-auto px-10 py-20">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="bg-slate-800/50 p-8 rounded-2xl border border-slate-700 hover:border-blue-500 transition">
                <div class="w-12 h-12 bg-blue-600/20 rounded-lg flex items-center justify-center mb-4 text-blue-500">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="Value1" />
                    </svg>
                </div>
                <h3 class="text-xl font-bold text-white mb-2">Instant Setup</h3>
                <p class="text-slate-400">Deploy your project with a single command. Zero configuration required.</p>
            </div>

  <div class="bg-slate-800/50 p-8 rounded-2xl border border-slate-700 hover:border-blue-500 transition">
                <div class="w-12 h-12 bg-purple-600/20 rounded-lg flex items-center justify-center mb-4 text-purple-500">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="Value2" />
                    </svg>
                </div>
                <h3 class="text-xl font-bold text-white mb-2">Edge Network</h3>
                <p class="text-slate-400">Your site stays fast everywhere in the world with our global CDN.</p>
            </div>

  <div class="bg-slate-800/50 p-8 rounded-2xl border border-slate-700 hover:border-blue-500 transition">
                <div class="w-12 h-12 bg-emerald-600/20 rounded-lg flex items-center justify-center mb-4 text-emerald-500">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="Value3" />
                    </svg>
                </div>
                <h3 class="text-xl font-bold text-white mb-2">Built-in Analytics</h3>
                <p class="text-slate-400">Privacy-focused insights that help you understand your traffic.</p>
            </div>
        </div>
    </section>

</body>
</html>
