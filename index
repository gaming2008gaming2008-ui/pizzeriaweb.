<!DOCTYPE html>
<html lang="it" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PizzeriaWeb - Vera Pizza Artigianale Italiana</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        pizzaRed: '#8B0000',
                        pizzaDarkRed: '#5c0000',
                        pizzaCream: '#FDFBF7',
                        pizzaGold: '#D4AF37',
                        pizzaDark: '#1A1A1A',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        serif: ['Playfair Display', 'serif']
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,600;0,700;1,400&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #FDFBF7; }
        ::-webkit-scrollbar-thumb { background: #8B0000; border-radius: 4px; }
    </style>
</head>
<body class="bg-pizzaCream text-pizzaDark font-sans antialiased selection:bg-pizzaRed selection:text-white">

    <!-- Toast Notification -->
    <div id="toast" class="fixed bottom-5 right-5 z-50 transform translate-y-32 opacity-0 transition-all duration-300 bg-pizzaDark text-pizzaCream px-6 py-3 rounded-xl shadow-2xl border border-pizzaGold/30 flex items-center space-x-3">
        <i id="toast-icon" class="fa-solid fa-circle-check text-pizzaGold text-lg"></i>
        <span id="toast-message" class="font-medium text-sm">Operazione completata!</span>
    </div>

    <!-- Navigation Bar -->
    <nav class="fixed top-0 left-0 w-full z-40 bg-pizzaDark/95 backdrop-blur-md text-pizzaCream border-b border-pizzaGold/20 transition-all" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <a href="#home" class="flex items-center space-x-2 group">
                    <div class="w-10 h-10 rounded-full bg-pizzaRed flex items-center justify-center text-pizzaGold shadow-lg group-hover:scale-105 transition-transform">
                        <i class="fa-solid fa-pizza-slice text-xl"></i>
                    </div>
                    <span class="font-serif text-2xl font-bold tracking-wide text-pizzaCream">Pizzeria<span class="text-pizzaGold">Web</span></span>
                </a>

                <div class="hidden lg:flex items-center space-x-7 font-medium text-sm tracking-wide">
                    <a href="#home" class="hover:text-pizzaGold transition-colors">Home</a>
                    <a href="#menu" class="hover:text-pizzaGold transition-colors">Menu</a>
                    <a href="#about" class="hover:text-pizzaGold transition-colors">Chi Siamo</a>
                    <a href="#booking" class="hover:text-pizzaGold transition-colors">Prenota Tavolo</a>
                    <a href="#github-guide" class="text-pizzaGold hover:underline flex items-center space-x-1.5"><i class="fa-brands fa-github"></i><span>Guida GitHub</span></a>
                    <a href="#contact" class="hover:text-pizzaGold transition-colors">Contatti</a>
                </div>

                <div class="flex items-center space-x-4">
                    <button onclick="toggleCart()" class="relative bg-pizzaRed/20 hover:bg-pizzaRed/40 border border-pizzaRed/40 p-2.5 rounded-full text-pizzaCream transition-all">
                        <i class="fa-solid fa-shopping-bag text-lg"></i>
                        <span id="cart-badge" class="absolute -top-1 -right-1 bg-pizzaGold text-pizzaDark font-bold text-xs w-5 h-5 rounded-full flex items-center justify-center shadow">0</span>
                    </button>
                    <button onclick="toggleMobileMenu()" class="lg:hidden text-pizzaCream hover:text-pizzaGold p-2">
                        <i class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden lg:hidden bg-pizzaDark border-b border-pizzaGold/20 px-4 pt-2 pb-6 space-y-3">
            <a href="#home" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Home</a>
            <a href="#menu" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Menu</a>
            <a href="#about" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Chi Siamo</a>
            <a href="#booking" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Prenota Tavolo</a>
            <a href="#github-guide" onclick="toggleMobileMenu()" class="block py-2 text-pizzaGold hover:text-white border-b border-white/5 flex items-center space-x-2"><i class="fa-brands fa-github"></i><span>Pubblica su GitHub Pages</span></a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold">Contatti</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative min-h-screen flex items-center justify-center bg-pizzaDark text-pizzaCream pt-20 overflow-hidden">
        <div class="absolute inset-0 z-0 opacity-40">
            <img src="https://placehold.co/1920x1080/1a1a1a/8b0000?text=+" class="w-full h-full object-cover" alt="Background">
            <div class="absolute inset-0 bg-gradient-to-t from-pizzaDark via-pizzaDark/70 to-transparent"></div>
        </div>

        <div class="relative z-10 max-w-5xl mx-auto px-4 text-center py-20">
            <span class="inline-block bg-pizzaRed/30 border border-pizzaRed/50 text-pizzaGold px-4 py-1.5 rounded-full text-xs font-semibold uppercase tracking-widest mb-6 animate-pulse">
                <i class="fa-solid fa-fire mr-2"></i> Tradizione dal Forno a Legna
            </span>
            <h1 class="font-serif text-4xl sm:text-6xl md:text-7xl font-bold tracking-tight mb-6 leading-tight">
                L'Autentica Pizza Italiana,<br>Preparata con <span class="text-pizzaGold italic">Passione</span>
            </h1>
            <p class="text-lg sm:text-xl text-gray-300 max-w-2xl mx-auto mb-10 font-light">
                Impasto a lunga lievitazione naturale, ingredienti freschi DOP e cottura impeccabile nel nostro forno a legna tradizionale.
            </p>
            <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                <a href="#menu" class="w-full sm:w-auto bg-pizzaRed hover:bg-pizzaDarkRed text-pizzaCream font-semibold px-8 py-4 rounded-xl shadow-lg transition-all flex items-center justify-center space-x-2">
                    <i class="fa-solid fa-utensils"></i>
                    <span>Esplora il Menu</span>
                </a>
                <a href="#github-guide" class="w-full sm:w-auto bg-pizzaGold hover:bg-yellow-500 text-pizzaDark font-bold px-8 py-4 rounded-xl shadow-lg transition-all flex items-center justify-center space-x-2">
                    <i class="fa-brands fa-github"></i>
                    <span>Carica su GitHub</span>
                </a>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu" class="py-24 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-3xl mx-auto mb-16">
            <span class="text-pizzaRed font-semibold tracking-widest text-sm uppercase">Il Nostro Catalogo</span>
            <h2 class="font-serif text-4xl sm:text-5xl font-bold mt-2 mb-4">Scegli la tua Pizza Preferita</h2>
            <p class="text-gray-600">Dalle classiche intramontabili alle nostre creazioni speciali artigianali. Ordina online o vieni a trovarci.</p>

            <div id="menu-filters" class="flex flex-wrap items-center justify-center gap-2 sm:gap-4 mt-8">
                <button onclick="filterMenu('all')" class="filter-btn active-filter bg-pizzaRed text-pizzaCream px-5 py-2.5 rounded-xl font-medium text-sm transition-all shadow-sm">Tutti</button>
                <button onclick="filterMenu('classiche')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all">Pizze Classiche</button>
                <button onclick="filterMenu('speciali')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all">Pizze Speciali</button>
                <button onclick="filterMenu('bevande')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all">Bevande</button>
                <button onclick="filterMenu('dolci')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all">Dolci</button>
            </div>
        </div>

        <div id="menu-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8"></div>
    </section>

    <!-- About Section -->
    <section id="about" class="bg-pizzaDark text-pizzaCream py-24 relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div>
                    <span class="text-pizzaGold font-semibold tracking-widest text-sm uppercase">La Nostra Storia</span>
                    <h2 class="font-serif text-4xl sm:text-5xl font-bold mt-2 mb-6">Tradizione, Famiglia e Autenticità dal 1998</h2>
                    <p class="text-gray-300 leading-relaxed mb-6">
                        PizzeriaWeb nasce dal sogno di portare l'autentica arte della pizza napoletana e italiana in un ambiente moderno e accogliente. Ogni giorno selezioniamo con cura i migliori ingredienti DOP: dal pomodoro San Marzano alla mozzarella di bufala campana.
                    </p>
                    <div class="grid grid-cols-2 gap-6 pt-4 border-t border-pizzaGold/20">
                        <div>
                            <span class="font-serif text-4xl font-bold text-pizzaGold">25+</span>
                            <p class="text-xs text-gray-400 mt-1">Anni di Esperienza</p>
                        </div>
                        <div>
                            <span class="font-serif text-4xl font-bold text-pizzaGold">100%</span>
                            <p class="text-xs text-gray-400 mt-1">Ingredienti Italiani DOP</p>
                        </div>
                    </div>
                </div>
                <div class="relative bg-pizzaDark border border-pizzaGold/30 rounded-2xl overflow-hidden shadow-2xl">
                    <img src="https://placehold.co/600x500/262626/d4af37?text=Forno+a+Legna+Artigianale" alt="Pizzaiolo" class="w-full h-auto object-cover">
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Section -->
    <section id="booking" class="py-24 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="bg-white border border-gray-200 rounded-3xl shadow-xl p-8 sm:p-12 relative overflow-hidden">
            <div class="text-center max-w-xl mx-auto mb-10">
                <span class="text-pizzaRed font-semibold tracking-widest text-sm uppercase">Riserva il tuo posto</span>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold mt-2 mb-3">Prenota un Tavolo</h2>
                <p class="text-gray-600 text-sm">Assicurati un'esperienza culinaria indimenticabile.</p>
            </div>

            <form id="booking-form" onsubmit="handleBooking(event)" class="space-y-6">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Nome e Cognome *</label>
                        <input type="text" id="book-name" required placeholder="Mario Rossi" class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed">
                    </div>
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Numero di Telefono *</label>
                        <input type="tel" id="book-phone" required placeholder="+39 333 1234567" class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed">
                    </div>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-6">
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Data *</label>
                        <input type="date" id="book-date" required class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed">
                    </div>
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Orario *</label>
                        <select id="book-time" required class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed">
                            <option value="">Seleziona orario</option>
                            <option value="19:00">19:00</option>
                            <option value="20:00">20:00</option>
                            <option value="21:00">21:00</option>
                            <option value="21:30">21:30</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Ospiti *</label>
                        <select id="book-guests" required class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed">
                            <option value="2" selected>2 Persone</option>
                            <option value="4">4 Persone</option>
                            <option value="6">6+ Persone</option>
                        </select>
                    </div>
                </div>
                <div class="text-center pt-4">
                    <button type="submit" class="w-full sm:w-auto bg-pizzaRed hover:bg-pizzaDarkRed text-pizzaCream font-semibold px-10 py-4 rounded-xl shadow-lg transition-all">
                        Conferma Prenotazione Tavolo
                    </button>
                </div>
            </form>
        </div>
    </section>

    <!-- GitHub Guide Section -->
    <section id="github-guide" class="bg-pizzaDark text-pizzaCream py-24 border-t border-pizzaGold/20">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-2xl mx-auto mb-16">
                <span class="text-pizzaGold font-semibold tracking-widest text-sm uppercase flex items-center justify-center space-x-2">
                    <i class="fa-brands fa-github text-xl"></i>
                    <span>Hosting Gratuito</span>
                </span>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold mt-2 mb-4">Come Pubblicare PizzeriaWeb su GitHub</h2>
                <p class="text-gray-300 text-sm">Segui questi semplici passaggi per mettere online il tuo sito web in pochi minuti.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-black/40 border border-pizzaGold/30 p-6 rounded-2xl">
                    <div class="w-10 h-10 rounded-full bg-pizzaGold text-pizzaDark font-bold flex items-center justify-center mb-4">1</div>
                    <h3 class="font-bold text-lg mb-2">Crea un Repository</h3>
                    <p class="text-sm text-gray-400">Vai su <a href="https://github.com" target="_blank" class="text-pizzaGold underline">GitHub</a>, crea un nuovo repository pubblico chiamato <code class="bg-gray-800 text-pizzaGold px-1.5 py-0.5 rounded">pizzeriaweb</code>.</p>
                </div>
                <div class="bg-black/40 border border-pizzaGold/30 p-6 rounded-2xl">
                    <div class="w-10 h-10 rounded-full bg-pizzaGold text-pizzaDark font-bold flex items-center justify-center mb-4">2</div>
                    <h3 class="font-bold text-lg mb-2">Carica il File HTML</h3>
                    <p class="text-sm text-gray-400">Rinomina questo codice in <code class="bg-gray-800 text-pizzaGold px-1.5 py-0.5 rounded">index.html</code> e caricalo nel repository premendo "Add file" -> "Upload files".</p>
                </div>
                <div class="bg-black/40 border border-pizzaGold/30 p-6 rounded-2xl">
                    <div class="w-10 h-10 rounded-full bg-pizzaGold text-pizzaDark font-bold flex items-center justify-center mb-4">3</div>
                    <h3 class="font-bold text-lg mb-2">Attiva GitHub Pages</h3>
                    <p class="text-sm text-gray-400">Vai nelle <strong>Settings</strong> del repository -> <strong>Pages</strong> -> Seleziona il branch <code class="bg-gray-800 text-pizzaGold px-1.5 py-0.5 rounded">main</code> e clicca Save!</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact & Map Section -->
    <section id="contact" class="bg-gray-100 py-24 border-t border-gray-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="text-pizzaRed font-semibold tracking-widest text-sm uppercase">Dove Siamo</span>
                <h2 class="font-serif text-4xl font-bold mt-2 mb-4">Contatti e Orari</h2>
                <p class="text-gray-600">Via Roma 42, 00184 Roma (RM) | Tel: +39 06 12345678</p>
            </div>
        </div>
    </section>

    <!-- Cart Modal -->
    <div id="cart-modal" class="fixed inset-0 z-50 overflow-hidden hidden">
        <div class="absolute inset-0 bg-black/50 backdrop-blur-sm" onclick="toggleCart()"></div>
        <div class="absolute inset-y-0 right-0 max-w-full flex pl-10">
            <div class="w-screen max-w-md bg-pizzaCream shadow-2xl flex flex-col">
                <div class="p-6 bg-pizzaDark text-pizzaCream flex items-center justify-between border-b border-pizzaGold/20">
                    <h3 class="font-serif text-lg font-bold">Il tuo Carrello</h3>
                    <button onclick="toggleCart()" class="text-gray-400 hover:text-white p-2"><i class="fa-solid fa-xmark text-xl"></i></button>
                </div>
                <div id="cart-items" class="flex-1 overflow-y-auto p-6 space-y-4"></div>
                <div class="p-6 bg-white border-t border-gray-200 space-y-4">
                    <div class="flex justify-between text-base font-bold">
                        <span>Totale</span>
                        <span id="cart-total" class="text-pizzaRed">€0.00</span>
                    </div>
                    <button onclick="checkout()" class="w-full bg-pizzaRed hover:bg-pizzaDarkRed text-pizzaCream font-semibold py-3.5 rounded-xl transition-all">Procedi all'Ordine</button>
                </div>
            </div>
        </div>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        const menuItems = [
            { id: 1, name: "Margherita Tradizionale", category: "classiche", description: "Pomodoro San Marzano DOP, Mozzarella di Bufala, Basilico fresco.", price: 8.50, image: "https://placehold.co/600x400/8b0000/fff?text=Margherita" },
            { id: 2, name: "Marinara Classica", category: "classiche", description: "Pomodoro San Marzano DOP, Aglio rosso, Origano e Olio EVO.", price: 6.50, image: "https://placehold.co/600x400/8b0000/fff?text=Marinara" },
            { id: 3, name: "Diavola Piccante", category: "classiche", description: "Pomodoro, fior di latte e Spianata calabra DOP.", price: 9.50, image: "https://placehold.co/600x400/8b0000/fff?text=Diavola" },
            { id: 4, name: "PizzeriaWeb Special", category: "speciali", description: "Crema di pistacchio di Bronte, Mortadella IGP, Stracciatella.", price: 13.00, image: "https://placehold.co/600x400/d4af37/1a1a1a?text=Pistacchio" },
            { id: 5, name: "Coca Cola 33cl", category: "bevande", description: "Lattina fredda da 33cl.", price: 3.50, image: "https://placehold.co/600x400/1a1a1a/fff?text=Coca+Cola" },
            { id: 6, name: "Tiramisù Artigianale", category: "dolci", description: "Savoiardi, espresso fresco e mascarpone.", price: 6.00, image: "https://placehold.co/600x400/5c0000/fff?text=Tiramisu" }
        ];

        let cart = [];

        document.addEventListener('DOMContentLoaded', () => { renderMenu('all'); });

        function toggleMobileMenu() { document.getElementById('mobile-menu').classList.toggle('hidden'); }

        function filterMenu(category) {
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.className = "filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all";
            });
            event.target.className = "filter-btn active-filter bg-pizzaRed text-pizzaCream px-5 py-2.5 rounded-xl font-medium text-sm transition-all shadow-sm";
            renderMenu(category);
        }

        function renderMenu(category) {
            const grid = document.getElementById('menu-grid');
            grid.innerHTML = '';
            const filtered = category === 'all' ? menuItems : menuItems.filter(item => item.category === category);
            filtered.forEach(item => {
                const card = document.createElement('div');
                card.className = "bg-white border border-gray-200 rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all flex flex-col justify-between group";
                card.innerHTML = `
                    <div>
                        <div class="h-48 overflow-hidden relative">
                            <img src="${item.image}" alt="${item.name}" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            <span class="absolute top-3 right-3 bg-pizzaDark/80 text-pizzaGold font-bold px-3 py-1 rounded-full text-xs">€${item.price.toFixed(2)}</span>
                        </div>
                        <div class="p-6">
                            <h3 class="font-serif font-bold text-xl text-gray-900 mb-2">${item.name}</h3>
                            <p class="text-gray-600 text-sm">${item.description}</p>
                        </div>
                    </div>
                    <div class="p-6 pt-0">
                        <button onclick="addToCart(${item.id})" class="w-full bg-pizzaRed/10 hover:bg-pizzaRed text-pizzaRed hover:text-pizzaCream font-semibold py-3 rounded-xl transition-all text-sm flex items-center justify-center space-x-2">
                            <i class="fa-solid fa-cart-plus"></i><span>Aggiungi al Carrello</span>
                        </button>
                    </div>`;
                grid.appendChild(card);
            });
        }

        function toggleCart() {
            document.getElementById('cart-modal').classList.toggle('hidden');
            updateCartUI();
        }

        function addToCart(id) {
            const product = menuItems.find(i => i.id === id);
            const existing = cart.find(i => i.id === id);
            if (existing) { existing.quantity += 1; } else { cart.push({ ...product, quantity: 1 }); }
            document.getElementById('cart-badge').innerText = cart.reduce((sum, item) => sum + item.quantity, 0);
            showToast(`${product.name} aggiunto!`);
        }

        function updateCartUI() {
            const container = document.getElementById('cart-items');
            container.innerHTML = '';
            if (cart.length === 0) {
                container.innerHTML = `<div class="text-center py-16 text-gray-400"><p class="text-sm">Il tuo carrello è vuoto</p></div>`;
                document.getElementById('cart-total').innerText = '€0.00';
                return;
            }
            let subtotal = 0;
            cart.forEach(item => {
                subtotal += item.price * item.quantity;
                const row = document.createElement('div');
                row.className = "flex items-center justify-between bg-pizzaCream/50 p-4 rounded-xl border border-gray-200";
                row.innerHTML = `<div class="flex-1 pr-4"><h4 class="font-bold text-sm">${item.name}</h4><span class="text-xs text-pizzaRed">€${item.price.toFixed(2)} x ${item.quantity}</span></div>`;
                container.appendChild(row);
            });
            document.getElementById('cart-total').innerText = `€${subtotal.toFixed(2)}`;
        }

        function checkout() {
            if (cart.length === 0) { showToast("Carrello vuoto!", "error"); return; }
            showToast("Ordine inviato con successo!");
            cart = [];
            document.getElementById('cart-badge').innerText = '0';
            toggleCart();
        }

        function handleBooking(event) {
            event.preventDefault();
            showToast("Tavolo prenotato con successo!");
            document.getElementById('booking-form').reset();
        }

        function showToast(message) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-message').innerText = message;
            toast.classList.remove('translate-y-32', 'opacity-0');
            setTimeout(() => { toast.classList.add('translate-y-32', 'opacity-0'); }, 3500);
        }
    </script>
</body>
</html>
```
eof
