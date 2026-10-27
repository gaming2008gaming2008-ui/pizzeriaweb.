# pizzeriaweb.
progetto di gruppo A-B-C
"ogni sviluppatore deve aggiungere due portate nel proprio menu"
-sviluppatore a: assegnato al menu pizze
-sviluppatore b: assegnato al menu doci
-sviluppatore c: assegnato al menu bevande
!DOCTYPE html>
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
        .font-serif {
            font-family: 'Playfair Display', serif;
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #FDFBF7;
        }
        ::-webkit-scrollbar-thumb {
            background: #8B0000;
            border-radius: 4px;
        }
    </style>
</head>
<body class="bg-pizzaCream text-pizzaDark font-sans antialiased selection:bg-pizzaRed selection:text-white">

    <!-- Notification / Toast Message Box -->
    <div id="toast" class="fixed bottom-5 right-5 z-50 transform translate-y-32 opacity-0 transition-all duration-300 bg-pizzaDark text-pizzaCream px-6 py-3 rounded-xl shadow-2xl border border-pizzaGold/30 flex items-center space-x-3">
        <i id="toast-icon" class="fa-solid fa-circle-check text-pizzaGold text-lg"></i>
        <span id="toast-message" class="font-medium text-sm">Messaggio inviato con successo!</span>
    </div>

    <!-- Navigation Bar -->
    <nav class="fixed top-0 left-0 w-full z-40 bg-pizzaDark/95 backdrop-blur-md text-pizzaCream border-b border-pizzaGold/20 transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Logo -->
                <a href="#" class="flex items-center space-x-2 group">
                    <div class="w-10 h-10 rounded-full bg-pizzaRed flex items-center justify-center text-pizzaGold shadow-lg group-hover:scale-105 transition-transform">
                        <i class="fa-solid fa-pizza-slice text-xl"></i>
                    </div>
                    <span class="font-serif text-2xl font-bold tracking-wide text-pizzaCream">Pizzeria<span class="text-pizzaGold">Web</span></span>
                </a>

                <!-- Desktop Navigation Links -->
                <div class="hidden md:flex items-center space-x-8 font-medium text-sm tracking-wide">
                    <a href="#home" class="hover:text-pizzaGold transition-colors">Home</a>
                    <a href="#menu" class="hover:text-pizzaGold transition-colors">Menu</a>
                    <a href="#about" class="hover:text-pizzaGold transition-colors">Chi Siamo</a>
                    <a href="#booking" class="hover:text-pizzaGold transition-colors">Prenota Tavolo</a>
                    <a href="#contact" class="hover:text-pizzaGold transition-colors">Contatti</a>
                </div>

                <!-- Right Actions: Cart & Mobile Menu Button -->
                <div class="flex items-center space-x-4">
                    <!-- Cart Trigger Button -->
                    <button onclick="toggleCart()" class="relative bg-pizzaRed/20 hover:bg-pizzaRed/40 border border-pizzaRed/40 p-2.5 rounded-full text-pizzaCream transition-all">
                        <i class="fa-solid fa-shopping-bag text-lg"></i>
                        <span id="cart-badge" class="absolute -top-1 -right-1 bg-pizzaGold text-pizzaDark font-bold text-xs w-5 h-5 rounded-full flex items-center justify-center shadow">0</span>
                    </button>

                    <!-- Mobile Menu Button -->
                    <button onclick="toggleMobileMenu()" class="md:hidden text-pizzaCream hover:text-pizzaGold focus:outline-none p-2">
                        <i id="mobile-menu-icon" class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden bg-pizzaDark border-b border-pizzaGold/20 px-4 pt-2 pb-6 space-y-3">
            <a href="#home" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Home</a>
            <a href="#menu" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Menu</a>
            <a href="#about" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Chi Siamo</a>
            <a href="#booking" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold border-b border-white/5">Prenota Tavolo</a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block py-2 text-pizzaCream hover:text-pizzaGold">Contatti</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative min-h-screen flex items-center justify-center bg-pizzaDark text-pizzaCream pt-20 overflow-hidden">
        <!-- Background Overlay with simulated Italian wood & oven warmth ambiance -->
        <div class="absolute inset-0 z-0 opacity-45">
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
                <a href="#menu" class="w-full sm:w-auto bg-pizzaRed hover:bg-pizzaDarkRed text-pizzaCream font-semibold px-8 py-4 rounded-xl shadow-lg hover:shadow-pizzaRed/30 transition-all transform hover:-translate-y-0.5 text-center flex items-center justify-center space-x-2">
                    <i class="fa-solid fa-utensils"></i>
                    <span>Esplora il Menu</span>
                </a>
                <a href="#booking" class="w-full sm:w-auto bg-transparent hover:bg-pizzaGold/10 border-2 border-pizzaGold text-pizzaGold font-semibold px-8 py-4 rounded-xl transition-all text-center flex items-center justify-center space-x-2">
                    <i class="fa-regular fa-calendar-check"></i>
                    <span>Prenota un Tavolo</span>
                </a>
            </div>

            <!-- Highlights badges -->
            <div class="grid grid-cols-2 md:grid-cols-3 gap-6 mt-16 max-w-3xl mx-auto border-t border-pizzaGold/20 pt-10 text-left sm:text-center">
                <div class="flex items-center space-x-3 justify-start sm:justify-center">
                    <div class="w-10 h-10 rounded-full bg-pizzaGold/10 border border-pizzaGold/30 flex items-center justify-center text-pizzaGold">
                        <i class="fa-solid fa-wheat-awn"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-sm">Farine Selezionate</h4>
                        <p class="text-xs text-gray-400">100% Italiane macinate a pietra</p>
                    </div>
                </div>
                <div class="flex items-center space-x-3 justify-start sm:justify-center">
                    <div class="w-10 h-10 rounded-full bg-pizzaGold/10 border border-pizzaGold/30 flex items-center justify-center text-pizzaGold">
                        <i class="fa-solid fa-clock"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-sm">48h Lievitazione</h4>
                        <p class="text-xs text-gray-400">Alta digeribilità garantita</p>
                    </div>
                </div>
                <div class="col-span-2 md:col-span-1 flex items-center space-x-3 justify-start sm:justify-center">
                    <div class="w-10 h-10 rounded-full bg-pizzaGold/10 border border-pizzaGold/30 flex items-center justify-center text-pizzaGold">
                        <i class="fa-solid fa-award"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-sm">Eccellenza DOP</h4>
                        <p class="text-xs text-gray-400">Mozzarella e Pomodoro San Marzano</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu" class="py-24 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-3xl mx-auto mb-16">
            <span class="text-pizzaRed font-semibold tracking-widest text-sm uppercase">Il Nostro Catalogo</span>
            <h2 class="font-serif text-4xl sm:text-5xl font-bold mt-2 mb-4">Scegli la tua Pizza Preferita</h2>
            <p class="text-gray-600">Dalle classiche intramontabili alle nostre creazioni speciali artigianali. Ordina online o vieni a trovarci.</p>

            <!-- Category Filter Buttons -->
            <div id="menu-filters" class="flex flex-wrap items-center justify-center gap-2 sm:gap-4 mt-8">
                <button onclick="filterMenu('all')" class="filter-btn active-filter bg-pizzaRed text-pizzaCream px-5 py-2.5 rounded-xl font-medium text-sm transition-all shadow-sm">Tutti</button>
                <button onclick="filterMenu('classiche')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all shadow-sm">Pizze Classiche</button>
                <button onclick="filterMenu('speciali')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all shadow-sm">Pizze Speciali</button>
                <button onclick="filterMenu('bevande')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all shadow-sm">Bevande</button>
                <button onclick="filterMenu('dolci')" class="filter-btn bg-white hover:bg-pizzaRed/10 text-pizzaDark border border-gray-200 px-5 py-2.5 rounded-xl font-medium text-sm transition-all shadow-sm">Dolci</button>
            </div>
        </div>

        <!-- Menu Items Grid -->
        <div id="menu-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Dynamic JavaScript insertion for menu items -->
        </div>
    </section>

    <!-- About Section ("Chi Siamo") -->
    <section id="about" class="bg-pizzaDark text-pizzaCream py-24 relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div>
                    <span class="text-pizzaGold font-semibold tracking-widest text-sm uppercase">La Nostra Storia</span>
                    <h2 class="font-serif text-4xl sm:text-5xl font-bold mt-2 mb-6">Tradizione, Famiglia e Autenticità dal 1998</h2>
                    <p class="text-gray-300 leading-relaxed mb-6">
                        PizzeriaWeb nasce dal sogno di portare l'autentica arte della pizza napoletana e italiana in un ambiente moderno e accogliente. Ogni giorno selezioniamo con cura i migliori ingredienti direttamente dai produttori locali e dalla Campania Felix: dal pomodoro San Marzano DOP alla vera mozzarella di bufala campana.
                    </p>
                    <p class="text-gray-300 leading-relaxed mb-8">
                        Il nostro segreto risiede nell'impasto: acqua purissima, sale marino, farine d'eccellenza e una lievitazione controllata di almeno 48 ore che garantisce scioglievolezza e altissima digeribilità.
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
                <div class="relative">
                    <div class="absolute -inset-2 bg-gradient-to-r from-pizzaRed to-pizzaGold rounded-2xl blur opacity-30"></div>
                    <div class="relative bg-pizzaDark border border-pizzaGold/30 rounded-2xl overflow-hidden shadow-2xl">
                        <img src="https://placehold.co/600x500/262626/d4af37?text=Forno+a+Legna+Artigianale" alt="Pizzaiolo al lavoro" class="w-full h-auto object-cover hover:scale-105 transition-transform duration-500">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Section ("Prenota Tavolo") -->
    <section id="booking" class="py-24 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="bg-white border border-gray-200 rounded-3xl shadow-xl p-8 sm:p-12 relative overflow-hidden">
            <div class="absolute top-0 right-0 w-40 h-40 bg-pizzaRed/5 rounded-bl-full pointer-events-none"></div>

            <div class="text-center max-w-xl mx-auto mb-10">
                <span class="text-pizzaRed font-semibold tracking-widest text-sm uppercase">Riserva il tuo posto</span>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold mt-2 mb-3">Prenota un Tavolo</h2>
                <p class="text-gray-600 text-sm">Assicurati un'esperienza culinaria indimenticabile. Riceverai conferma immediata.</p>
            </div>

            <form id="booking-form" onsubmit="handleBooking(event)" class="space-y-6">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Nome e Cognome *</label>
                        <input type="text" id="book-name" required placeholder="Mario Rossi" class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed transition-colors">
                    </div>
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Numero di Telefono *</label>
                        <input type="tel" id="book-phone" required placeholder="+39 333 1234567" class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed transition-colors">
                    </div>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-3 gap-6">
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Data *</label>
                        <input type="date" id="book-date" required class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed transition-colors">
                    </div>
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Orario *</label>
                        <select id="book-time" required class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed transition-colors">
                            <option value="">Seleziona orario</option>
                            <option value="19:00">19:00</option>
                            <option value="19:30">19:30</option>
                            <option value="20:00">20:00</option>
                            <option value="20:30">20:30</option>
                            <option value="21:00">21:00</option>
                            <option value="21:30">21:30</option>
                            <option value="22:00">22:00</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Numero Ospiti *</label>
                        <select id="book-guests" required class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed transition-colors">
                            <option value="1">1 Persona</option>
                            <option value="2" selected>2 Persone</option>
                            <option value="3">3 Persone</option>
                            <option value="4">4 Persone</option>
                            <option value="5">5 Persone</option>
                            <option value="6+">6+ Persone (Gruppo)</option>
                        </select>
                    </div>
                </div>

                <div>
                    <label class="block text-xs font-bold uppercase tracking-wider text-gray-700 mb-2">Note o Richieste Speciali (opzionale)</label>
                    <textarea id="book-notes" rows="3" placeholder="Es. Seggiolone per bambini, intolleranze alimentari..." class="w-full bg-pizzaCream/50 border border-gray-300 rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-pizzaRed transition-colors"></textarea>
                </div>

                <div class="text-center pt-4">
                    <button type="submit" class="w-full sm:w-auto bg-pizzaRed hover:bg-pizzaDarkRed text-pizzaCream font-semibold px-10 py-4 rounded-xl shadow-lg transition-all transform hover:-translate-y-0.5">
                        Conferma Prenotazione Tavolo
                    </button>
                </div>
            </form>
        </div>
    </section>

    <!-- Contact & Map Section -->
    <section id="contact" class="bg-gray-100 py-24 border-t border-gray-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="text-pizzaRed font-semibold tracking-widest text-sm uppercase">Dove Siamo</span>
                <h2 class="font-serif text-4xl font-bold mt-2 mb-4">Contatti e Orari di Apertura</h2>
                <p class="text-gray-600">Vieni a trovarci in pizzeria o contattaci per qualsiasi informazione o asporto.</p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                <!-- Info Cards -->
                <div class="bg-white p-8 rounded-2xl shadow-sm border border-gray-200 space-y-6">
                    <div class="flex items-start space-x-4">
                        <div class="w-12 h-12 rounded-xl bg-pizzaRed/10 text-pizzaRed flex items-center justify-center shrink-0">
                            <i class="fa-solid fa-location-dot text-lg"></i>
                        </div>
                        <div>
                            <h4 class="font-bold text-gray-900">Indirizzo</h4>
                            <p class="text-sm text-gray-600 mt-1">Via Roma 42, 00184 Roma (RM)</p>
                        </div>
                    </div>
                    <div class="flex items-start space-x-4">
                        <div class="w-12 h-12 rounded-xl bg-pizzaRed/10 text-pizzaRed flex items-center justify-center shrink-0">
                            <i class="fa-solid fa-phone text-lg"></i>
                        </div>
                        <div>
                            <h4 class="font-bold text-gray-900">Telefono / Ordini</h4>
                            <p class="text-sm text-gray-600 mt-1">+39 06 12345678</p>
                        </div>
                    </div>
                    <div class="flex items-start space-x-4">
                        <div class="w-12 h-12 rounded-xl bg-pizzaRed/10 text-pizzaRed flex items-center justify-center shrink-0">
                            <i class="fa-solid fa-clock text-lg"></i>
                        </div>
                        <div>
                            <h4 class="font-bold text-gray-900">Orari di Apertura</h4>
                            <p class="text-sm text-gray-600 mt-1">Mar - Dom: 19:00 - 23:30<br>Lunedì: Chiuso</p>
                        </div>
                    </div>
                </div>

                <!-- Simulated Map -->
                <div class="lg:col-span-2 bg-white rounded-2xl shadow-sm border border-gray-200 overflow-hidden relative min-h-[350px] flex items-center justify-center bg-gray-200">
                    <img src="https://placehold.co/900x450/e2e8f0/475569?text=Mappa+Interattiva+PizzeriaWeb+-+Via+Roma+42,+Roma" alt="Mappa PizzeriaWeb" class="w-full h-full object-cover">
                    <div class="absolute inset-0 bg-pizzaDark/10 flex items-center justify-center pointer-events-none">
                        <div class="bg-pizzaDark text-pizzaCream px-6 py-3 rounded-xl shadow-2xl flex items-center space-x-3 border border-pizzaGold/40 pointer-events-auto">
                            <i class="fa-solid fa-map-pin text-pizzaRed text-xl animate-bounce"></i>
                            <div>
                                <p class="font-bold text-xs">PizzeriaWeb Roma</p>
                                <a href="https://maps.google.com" target="_blank" class="text-xs text-pizzaGold underline hover:text-white">Apri su Google Maps</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Cart Slide-Over / Modal -->
    <div id="cart-modal" class="fixed inset-0 z-50 overflow-hidden hidden">
        <div class="absolute inset-0 bg-black/50 backdrop-blur-sm transition-opacity" onclick="toggleCart()"></div>
        <div class="absolute inset-y-0 right-0 max-w-full flex pl-10">
            <div class="w-screen max-w-md bg-pizzaCream shadow-2xl flex flex-col">
                <!-- Cart Header -->
                <div class="p-6 bg-pizzaDark text-pizzaCream flex items-center justify-between border-b border-pizzaGold/20">
                    <div class="flex items-center space-x-2">
                        <i class="fa-solid fa-shopping-bag text-pizzaGold"></i>
                        <h3 class="font-serif text-lg font-bold">Il tuo Carrello</h3>
                    </div>
                    <button onclick="toggleCart()" class="text-gray-400 hover:text-white p-2">
                        <i class="fa-solid fa-xmark text-xl"></i>
                    </button>
                </div>

                <!-- Cart Items List -->
                <div id="cart-items" class="flex-1 overflow-y-auto p-6 space-y-4">
                    <!-- Dynamic cart list -->
                </div>

                <!-- Cart Footer / Checkout Summary -->
                <div class="p-6 bg-white border-t border-gray-200 space-y-4">
                    <div class="flex justify-between text-sm">
                        <span class="text-gray-600">Subtotale</span>
                        <span id="cart-subtotal" class="font-bold">€0.00</span>
                    </div>
                    <div class="flex justify-between text-sm">
                        <span class="text-gray-600">Consegna a domicilio</span>
                        <span class="font-bold text-green-600">Gratuita</span>
                    </div>
                    <div class="border-t border-gray-200 pt-3 flex justify-between text-base font-bold">
                        <span>Totale</span>
                        <span id="cart-total" class="text-pizzaRed">€0.00</span>
                    </div>

                    <button onclick="checkout()" class="w-full bg-pizzaRed hover:bg-pizzaDarkRed text-pizzaCream font-semibold py-3.5 rounded-xl shadow-md transition-all text-center flex items-center justify-center space-x-2">
                        <span>Procedi all'Ordine</span>
                        <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-pizzaDark text-pizzaCream border-t border-pizzaGold/20 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-6">
            <div class="flex items-center justify-center space-x-2">
                <div class="w-8 h-8 rounded-full bg-pizzaRed flex items-center justify-center text-pizzaGold">
                    <i class="fa-solid fa-pizza-slice"></i>
                </div>
                <span class="font-serif text-xl font-bold">Pizzeria<span class="text-pizzaGold">Web</span></span>
            </div>
            <p class="text-sm text-gray-400 max-w-md mx-auto">La vera pizza artigianale italiana direttamente a casa tua o gustata nel nostro locale accogliente.</p>
            <div class="flex justify-center space-x-6 text-xl">
                <a href="#" class="text-gray-400 hover:text-pizzaGold transition-colors"><i class="fa-brands fa-facebook"></i></a>
                <a href="#" class="text-gray-400 hover:text-pizzaGold transition-colors"><i class="fa-brands fa-instagram"></i></a>
                <a href="#" class="text-gray-400 hover:text-pizzaGold transition-colors"><i class="fa-brands fa-tripadvisor"></i></a>
            </div>
            <div class="border-t border-white/10 pt-6 text-xs text-gray-500">
                &copy; 2026 PizzeriaWeb. Tutti i diritti riservati. Sviluppato con passione per l'eccellenza italiana.
            </div>
        </div>
    </footer>

    <!-- JavaScript Application Logic -->
    <script>
        // Menu Database
        const menuItems = [
            {
                id: 1,
                name: "Margherita Tradizionale",
                category: "classiche",
                description: "Pomodoro San Marzano DOP, Mozzarella di Bufala, Basilico fresco e Olio EVO.",
                price: 8.50,
                image: "https://placehold.co/600x400/8b0000/fff?text=Margherita"
            },
            {
                id: 2,
                name: "Marinara Classica",
                category: "classiche",
                description: "Pomodoro San Marzano DOP, Aglio rosso di Sulmona, Origano di montagna e Olio EVO.",
                price: 6.50,
                image: "https://placehold.co/600x400/8b0000/fff?text=Marinara"
            },
            {
                id: 3,
                name: "Diavola Piccante",
                category: "classiche",
                description: "Pomodoro San Marzano DOP, Mozzarella fior di latte e Spianata calabra DOP piccante.",
                price: 9.50,
                image: "https://placehold.co/600x400/8b0000/fff?text=Diavola"
            },
            {
                id: 4,
                name: "Quattro Formaggi d'Autore",
                category: "classiche",
                description: "Fior di latte, Gorgonzola DOP, Fontina valdostana e Parmigiano Reggiano 24 mesi.",
                price: 10.50,
                image: "https://placehold.co/600x400/8b0000/fff?text=4+Formaggi"
            },
            {
                id: 5,
                name: "PizzeriaWeb Special",
                category: "speciali",
                description: "Crema di pistacchio di Bronte, Mortadella IGP, Stracciatella di burrata e granella di pistacchio.",
                price: 13.00,
                image: "https://placehold.co/600x400/d4af37/1a1a1a?text=Pistacchio+e+Mortadella"
            },
            {
                id: 6,
                name: "Tartufo e Funghi Porcini",
                category: "speciali",
                description: "Carpaccio di tartufo nero estivo, funghi porcini freschi saltati, fior di latte e timo.",
                price: 14.50,
                image: "https://placehold.co/600x400/d4af37/1a1a1a?text=Tartufo+e+Porcini"
            },
            {
                id: 7,
                name: "Capricciosa del Re",
                category: "speciali",
                description: "Pomodoro, fior di latte, prosciutto cotto artigianale, funghi champignon, carciofi e olive nere.",
                price: 11.00,
                image: "https://placehold.co/600x400/d4af37/1a1a1a?text=Capricciosa"
            },
            {
                id: 8,
                name: "Coca Cola 33cl",
                category: "bevande",
                description: "Lattina da 33cl in vetro o alluminio fredda.",
                price: 3.50,
                image: "https://placehold.co/600x400/1a1a1a/fff?text=Coca+Cola"
            },
            {
                id: 9,
                name: "Birra Artigianale Italiana 33cl",
                category: "bevande",
                description: "Bionda o Rossa artigianale non filtrata.",
                price: 5.50,
                image: "https://placehold.co/600x400/1a1a1a/fff?text=Birra+Artigianale"
            },
            {
                id: 10,
                name: "Acqua Naturale / Frizzante 0.75L",
                category: "bevande",
                description: "Bottiglia in vetro purissima.",
                price: 2.50,
                image: "https://placehold.co/600x400/1a1a1a/fff?text=Acqua"
            },
            {
                id: 11,
                name: "Tiramisù Artigianale",
                category: "dolci",
                description: "Savoiardi inzuppati nel caffè espresso, mascarpone fresco e cacao amaro.",
                price: 6.00,
                image: "https://placehold.co/600x400/5c0000/fff?text=Tiramisu"
            },
            {
                id: 12,
                name: "Pizza Dolce con Nutella",
                category: "dolci",
                description: "Base pizza soffice al forno farcita con abbondante Nutella e granella di nocciole.",
                price: 7.50,
                image: "https://placehold.co/600x400/5c0000/fff?text=Pizza+Nutella"
            }
        ];

        // Cart State
        let cart = [];

        // Initialize Menu Rendering
        document.addEventListener('DOMContentLoaded', () => {
            renderMenu('all');
        });

        // Toggle Mobile Menu
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // Filter Menu
        function filterMenu(category) {
            // Update button styles
            const buttons = document.querySelectorAll('.filter-btn');
            buttons.forEach(btn => {
                btn.classList.remove('bg-pizzaRed', 'text-pizzaCream');
                btn.classList.add('bg-white', 'text-pizzaDark', 'border', 'border-gray-200');
            });
            event.target.classList.remove('bg-white', 'text-pizzaDark', 'border');
            event.target.classList.add('bg-pizzaRed', 'text-pizzaCream');

            renderMenu(category);
        }

        // Render Menu Items
        function renderMenu(category) {
            const grid = document.getElementById('menu-grid');
            grid.innerHTML = '';

            const filtered = category === 'all' 
                ? menuItems 
                : menuItems.filter(item => item.category === category);

            filtered.forEach(item => {
                const card = document.createElement('div');
                card.className = "bg-white border border-gray-200 rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-300 flex flex-col justify-between group";
                card.innerHTML = `
                    <div>
                        <div class="h-48 overflow-hidden relative">
                            <img src="${item.image}" alt="${item.name}" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            <span class="absolute top-3 right-3 bg-pizzaDark/80 backdrop-blur-sm text-pizzaGold font-bold px-3 py-1 rounded-full text-xs">
                                €${item.price.toFixed(2)}
                            </span>
                        </div>
                        <div class="p-6">
                            <h3 class="font-serif font-bold text-xl text-gray-900 mb-2">${item.name}</h3>
                            <p class="text-gray-600 text-sm leading-relaxed">${item.description}</p>
                        </div>
                    </div>
                    <div class="p-6 pt-0">
                        <button onclick="addToCart(${item.id})" class="w-full bg-pizzaRed/10 hover:bg-pizzaRed text-pizzaRed hover:text-pizzaCream font-semibold py-3 rounded-xl transition-all text-sm flex items-center justify-center space-x-2">
                            <i class="fa-solid fa-cart-plus"></i>
                            <span>Aggiungi al Carrello</span>
                        </button>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Cart Management
        function toggleCart() {
            const modal = document.getElementById('cart-modal');
            modal.classList.toggle('hidden');
            updateCartUI();
        }

        function addToCart(id) {
            const product = menuItems.find(i => i.id === id);
            const existing = cart.find(i => i.id === id);

            if (existing) {
                existing.quantity += 1;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateCartBadge();
            showToast(`${product.name} aggiunto al carrello!`);
        }

        function updateCartBadge() {
            const totalCount = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById('cart-badge').innerText = totalCount;
        }

        function updateCartUI() {
            const container = document.getElementById('cart-items');
            container.innerHTML = '';

            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-16 text-gray-400">
                        <i class="fa-solid fa-basket-shopping text-4xl mb-3 text-gray-300"></i>
                        <p class="text-sm">Il tuo carrello è vuoto</p>
                    </div>
                `;
                document.getElementById('cart-subtotal').innerText = '€0.00';
                document.getElementById('cart-total').innerText = '€0.00';
                return;
            }

            let subtotal = 0;

            cart.forEach(item => {
                subtotal += item.price * item.quantity;
                const row = document.createElement('div');
                row.className = "flex items-center justify-between bg-pizzaCream/50 p-4 rounded-xl border border-gray-200";
                row.innerHTML = `
                    <div class="flex-1 pr-4">
                        <h4 class="font-bold text-sm text-gray-900">${item.name}</h4>
                        <span class="text-xs text-pizzaRed font-semibold">€${item.price.toFixed(2)}</span>
                    </div>
                    <div class="flex items-center space-x-2">
                        <button onclick="changeQuantity(${item.id}, -1)" class="w-7 h-7 bg-white border border-gray-300 rounded-lg flex items-center justify-center text-xs font-bold hover:bg-gray-100">-</button>
                        <span class="text-sm font-bold w-5 text-center">${item.quantity}</span>
                        <button onclick="changeQuantity(${item.id}, 1)" class="w-7 h-7 bg-white border border-gray-300 rounded-lg flex items-center justify-center text-xs font-bold hover:bg-gray-100">+</button>
                    </div>
                `;
                container.appendChild(row);
            });

            document.getElementById('cart-subtotal').innerText = `€${subtotal.toFixed(2)}`;
            document.getElementById('cart-total').innerText = `€${subtotal.toFixed(2)}`;
        }

        function changeQuantity(id, delta) {
            const item = cart.find(i => i.id === id);
            if (item) {
                item.quantity += delta;
                if (item.quantity <= 0) {
                    cart = cart.filter(i => i.id !== id);
                }
            }
            updateCartBadge();
            updateCartUI();
        }

        function checkout() {
            if (cart.length === 0) {
                showToast("Il carrello è vuoto!", "error");
                return;
            }
            showToast("Ordine inviato con successo! Ti ringraziamo.");
            cart = [];
            updateCartBadge();
            toggleCart();
        }

        // Booking Form Handler
        function handleBooking(event) {
            event.preventDefault();
            const name = document.getElementById('book-name').value;
            const date = document.getElementById('book-date').value;
            const time = document.getElementById('book-time').value;
            const guests = document.getElementById('book-guests').value;

            showToast(`Tavolo prenotato per ${name} (${guests} persone) il ${date} alle ${time}!`);
            document.getElementById('booking-form').reset();
        }

        // Toast Notification Function
        function showToast(message, type = 'success') {
            const toast = document.getElementById('toast');
            const msgEl = document.getElementById('toast-message');
            const iconEl = document.getElementById('toast-icon');

            msgEl.innerText = message;
            if (type === 'success') {
                iconEl.className = "fa-solid fa-circle-check text-pizzaGold text-lg";
            } else {
                iconEl.className = "fa-solid fa-circle-exclamation text-red-500 text-lg";
            }

            toast.classList.remove('translate-y-32', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-32', 'opacity-0');
            }, 3500);
        }
    </script>
</body>
</html>
