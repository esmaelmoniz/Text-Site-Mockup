<!DOCTYPE html>
<html lang="pt-PT">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Black Cars - Aluguer de Viaturas Exclusivas</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Raleway:wght@300;400;600;800&display=swap');

        :root {
            --gold-accent: #d4af37;
        }

        body {
            font-family: 'Raleway', sans-serif;
            background-color: #0f0f0f;
            color: #f3f3f3;
        }

        h1, h2, h3, .serif-font {
            font-family: 'Playfair Display', serif;
        }

        .gold-text {
            color: var(--gold-accent);
        }

        .gold-border {
            border-color: var(--gold-accent);
        }

        .gold-bg {
            background-color: var(--gold-accent);
        }

        .hover-gold:hover {
            color: var(--gold-accent);
        }

        .btn-primary {
            background: linear-gradient(45deg, #b8860b, #d4af37);
            color: #000;
            transition: all 0.3s ease;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(212, 175, 55, 0.4);
        }

        .car-card {
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .car-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.5), 0 10px 10px -5px rgba(0, 0, 0, 0.3);
        }

        /* Modal Styles */
        #bookingModal {
            backdrop-filter: blur(5px);
        }
        
        .placeholder-logo {
            letter-spacing: 0.15em;
            text-transform: uppercase;
            border: 2px solid #d4af37;
            padding: 5px 15px;
        }
    </style>
</head>
<body class="antialiased min-h-screen flex flex-col">

    <!-- Navbar -->
    <nav class="fixed w-full z-50 bg-black/90 backdrop-blur-md border-b border-gray-800">
        <div class="container mx-auto px-6 py-4 flex justify-between items-center">
            <!-- Logo area: Emulating the user's logo style -->
            <a href="#" class="flex items-center gap-2 group">
                <div class="serif-font text-2xl font-bold text-white group-hover:text-[#d4af37] transition-colors duration-300">
                    BLACK <span class="gold-text">CARS</span>
                </div>
            </a>
            
            <div class="hidden md:flex space-x-8 text-sm font-semibold tracking-widest uppercase">
                <a href="#home" class="hover-gold transition-colors">Início</a>
                <a href="#catalog" class="hover-gold transition-colors">A Frota</a>
                <a href="#services" class="hover-gold transition-colors">Serviços</a>
                <a href="#contact" class="hover-gold transition-colors">Contactos</a>
            </div>

            <button onclick="document.getElementById('catalog').scrollIntoView({behavior: 'smooth'})" class="hidden md:block border border-[#d4af37] text-[#d4af37] px-6 py-2 hover:bg-[#d4af37] hover:text-black transition-all uppercase text-xs tracking-widest font-bold">
                Reservar
            </button>

            <!-- Mobile Menu Button -->
            <button class="md:hidden text-white" onclick="toggleMobileMenu()">
                <i class="fas fa-bars text-2xl"></i>
            </button>
        </div>
        
        <!-- Mobile Menu -->
        <div id="mobileMenu" class="hidden bg-black border-t border-gray-800 absolute w-full p-6 md:hidden">
            <div class="flex flex-col space-y-4 text-center">
                <a href="#home" class="text-white hover:text-[#d4af37]">Início</a>
                <a href="#catalog" class="text-white hover:text-[#d4af37]">A Frota</a>
                <button onclick="document.getElementById('catalog').scrollIntoView()" class="mt-4 bg-[#d4af37] text-black py-2 font-bold">RESERVAR</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative h-screen flex items-center justify-center overflow-hidden">
        <!-- Background Image Fallback using CSS Gradient and a subtle pattern if image fails -->
        <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1492144534655-ae79c964c9d7?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80')] bg-cover bg-center"></div>
        <div class="absolute inset-0 bg-gradient-to-t from-[#0f0f0f] via-black/70 to-black/30"></div>

        <div class="relative z-10 text-center px-6 max-w-4xl mx-auto">
            <p class="text-[#d4af37] tracking-[0.3em] uppercase text-sm mb-4 font-bold animate-pulse">Experiência Premium</p>
            <h1 class="text-5xl md:text-7xl font-bold text-white mb-6 leading-tight">
                Domine a Estrada com <br/><span class="italic text-gray-400">Elegância</span>
            </h1>
            <p class="text-gray-300 text-lg mb-10 max-w-2xl mx-auto font-light">
                A Black Cars oferece uma seleção exclusiva de viaturas de alta performance para quem não aceita menos que a excelência.
            </p>
            <div class="flex flex-col md:flex-row gap-4 justify-center">
                <a href="#catalog" class="btn-primary px-8 py-4 text-sm font-bold uppercase tracking-wider rounded-sm">Ver Catálogo</a>
                <a href="#contact" class="border border-white text-white px-8 py-4 text-sm font-bold uppercase tracking-wider hover:bg-white hover:text-black transition-all rounded-sm">Fale Connosco</a>
            </div>
        </div>
    </section>

    <!-- Catalog Section -->
    <section id="catalog" class="py-24 px-6 container mx-auto">
        <div class="text-center mb-16">
            <h2 class="text-4xl text-white mb-4">A Nossa Coleção</h2>
            <div class="w-24 h-1 bg-[#d4af37] mx-auto"></div>
            <p class="mt-4 text-gray-400">Escolha a sua máquina para a próxima jornada.</p>
        </div>

        <!-- Filter Buttons -->
        <div class="flex flex-wrap justify-center gap-4 mb-12">
            <button onclick="filterCars('all')" class="filter-btn active text-sm uppercase tracking-widest px-6 py-2 border border-gray-700 text-gray-400 hover:border-[#d4af37] hover:text-[#d4af37] transition-all rounded-full" data-filter="all">Todas</button>
            <button onclick="filterCars('suv')" class="filter-btn text-sm uppercase tracking-widest px-6 py-2 border border-gray-700 text-gray-400 hover:border-[#d4af37] hover:text-[#d4af37] transition-all rounded-full" data-filter="suv">SUVs</button>
            <button onclick="filterCars('sport')" class="filter-btn text-sm uppercase tracking-widest px-6 py-2 border border-gray-700 text-gray-400 hover:border-[#d4af37] hover:text-[#d4af37] transition-all rounded-full" data-filter="sport">Desportivos</button>
            <button onclick="filterCars('luxury')" class="filter-btn text-sm uppercase tracking-widest px-6 py-2 border border-gray-700 text-gray-400 hover:border-[#d4af37] hover:text-[#d4af37] transition-all rounded-full" data-filter="luxury">Executivo</button>
        </div>

        <!-- Cars Grid -->
        <div id="carGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Cars will be injected via JS -->
        </div>
    </section>

    <!-- Features Section -->
    <section class="bg-neutral-900 py-20 border-t border-gray-800">
        <div class="container mx-auto px-6 grid grid-cols-1 md:grid-cols-3 gap-12 text-center">
            <div class="p-6">
                <i class="fas fa-certificate text-4xl text-[#d4af37] mb-6"></i>
                <h3 class="text-xl font-bold mb-3 text-white">Garantia de Qualidade</h3>
                <p class="text-gray-500 text-sm">Todas as viaturas são inspecionadas rigorosamente antes de cada entrega.</p>
            </div>
            <div class="p-6">
                <i class="fas fa-clock text-4xl text-[#d4af37] mb-6"></i>
                <h3 class="text-xl font-bold mb-3 text-white">Suporte 24/7</h3>
                <p class="text-gray-500 text-sm">Assistência em viagem e linha de apoio dedicada a qualquer hora do dia.</p>
            </div>
            <div class="p-6">
                <i class="fas fa-concierge-bell text-4xl text-[#d4af37] mb-6"></i>
                <h3 class="text-xl font-bold mb-3 text-white">Serviço VIP</h3>
                <p class="text-gray-500 text-sm">Entrega e recolha da viatura no local da sua preferência.</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact" class="bg-black py-12 border-t border-[#d4af37]">
        <div class="container mx-auto px-6">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-6 md:mb-0">
                    <div class="serif-font text-3xl font-bold text-white mb-2">
                        BLACK <span class="gold-text">CARS</span>
                    </div>
                    <p class="text-gray-500 text-sm">Onde a performance encontra o prestígio.</p>
                </div>
                
                <div class="flex space-x-6">
                    <a href="#" class="text-gray-400 hover:text-[#d4af37] transition-colors"><i class="fab fa-instagram text-2xl"></i></a>
                    <a href="#" class="text-gray-400 hover:text-[#d4af37] transition-colors"><i class="fab fa-facebook text-2xl"></i></a>
                    <a href="#" class="text-gray-400 hover:text-[#d4af37] transition-colors"><i class="fab fa-whatsapp text-2xl"></i></a>
                </div>
            </div>
            <div class="mt-8 text-center text-gray-600 text-xs border-t border-gray-900 pt-8">
                &copy; 2024 Black Cars. Todos os direitos reservados. Design conceptual.
            </div>
        </div>
    </footer>

    <!-- Booking Modal -->
    <div id="bookingModal" class="fixed inset-0 z-[60] hidden flex items-center justify-center bg-black/80">
        <div class="bg-neutral-900 border border-gray-700 p-8 rounded-lg max-w-md w-full mx-4 relative shadow-2xl">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-500 hover:text-white">
                <i class="fas fa-times text-xl"></i>
            </button>
            
            <h3 class="text-2xl serif-font text-white mb-1">Reservar Viatura</h3>
            <p id="modalCarName" class="text-[#d4af37] font-bold mb-6 text-lg"></p>
            
            <form onsubmit="event.preventDefault(); submitBooking();" class="space-y-4">
                <div>
                    <label class="block text-gray-400 text-xs uppercase tracking-wide mb-2">Nome Completo</label>
                    <input type="text" required class="w-full bg-black border border-gray-700 text-white p-3 rounded focus:outline-none focus:border-[#d4af37]">
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-gray-400 text-xs uppercase tracking-wide mb-2">Data Início</label>
                        <input type="date" required class="w-full bg-black border border-gray-700 text-white p-3 rounded focus:outline-none focus:border-[#d4af37] text-gray-400">
                    </div>
                    <div>
                        <label class="block text-gray-400 text-xs uppercase tracking-wide mb-2">Dias</label>
                        <input type="number" min="1" value="1" class="w-full bg-black border border-gray-700 text-white p-3 rounded focus:outline-none focus:border-[#d4af37]">
                    </div>
                </div>
                <div>
                    <label class="block text-gray-400 text-xs uppercase tracking-wide mb-2">Telefone</label>
                    <input type="tel" required class="w-full bg-black border border-gray-700 text-white p-3 rounded focus:outline-none focus:border-[#d4af37]">
                </div>
                
                <button type="submit" class="w-full btn-primary py-3 font-bold mt-4 rounded">SOLICITAR COTAÇÃO</button>
            </form>
        </div>
    </div>

    <!-- Success Message Toast -->
    <div id="toast" class="fixed bottom-10 right-10 bg-green-600 text-white px-6 py-4 rounded shadow-2xl transform translate-y-20 opacity-0 transition-all duration-300 z-[70] flex items-center gap-3">
        <i class="fas fa-check-circle text-xl"></i>
        <div>
            <h4 class="font-bold">Sucesso!</h4>
            <p class="text-sm">O seu pedido foi enviado.</p>
        </div>
    </div>

    <script>
        // Fictional Car Data with distinct "Black Cars" aesthetic names
        const cars = [
            {
                id: 1,
                name: "Obsidian Phantom GT",
                category: "sport",
                price: "450",
                image: "https://images.unsplash.com/photo-1617788138017-80ad40651399?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
                specs: {
                    seats: 2,
                    trans: "Auto",
                    fuel: "Gasolina",
                    hp: "580 CV"
                }
            },
            {
                id: 2,
                name: "Titanium Rover X",
                category: "suv",
                price: "320",
                image: "https://images.unsplash.com/photo-1633512217101-9c60df58025c?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
                specs: {
                    seats: 7,
                    trans: "Auto",
                    fuel: "Híbrido",
                    hp: "400 CV"
                }
            },
            {
                id: 3,
                name: "Midnight Executive",
                category: "luxury",
                price: "280",
                image: "https://images.unsplash.com/photo-1555215695-3004980adade?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
                specs: {
                    seats: 5,
                    trans: "Auto",
                    fuel: "Diesel",
                    hp: "320 CV"
                }
            },
            {
                id: 4,
                name: "Shadow Velocity",
                category: "sport",
                price: "520",
                image: "https://images.unsplash.com/photo-1503376763036-066120622c74?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
                specs: {
                    seats: 2,
                    trans: "Seq",
                    fuel: "Gasolina",
                    hp: "620 CV"
                }
            },
            {
                id: 5,
                name: "Onyx Diplomat",
                category: "luxury",
                price: "350",
                image: "https://images.unsplash.com/photo-1563720223185-11003d516935?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
                specs: {
                    seats: 4,
                    trans: "Auto",
                    fuel: "Elétrico",
                    hp: "450 CV"
                }
            },
            {
                id: 6,
                name: "Vogue Black Edition",
                category: "suv",
                price: "300",
                image: "https://images.unsplash.com/photo-1533473359331-0135ef1b58bf?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
                specs: {
                    seats: 5,
                    trans: "Auto",
                    fuel: "Diesel",
                    hp: "300 CV"
                }
            }
        ];

        // Render Cars
        function renderCars(filter = 'all') {
            const grid = document.getElementById('carGrid');
            grid.innerHTML = '';
            
            const filteredCars = filter === 'all' ? cars : cars.filter(car => car.category === filter);

            filteredCars.forEach(car => {
                const card = document.createElement('div');
                card.className = 'car-card bg-neutral-800 rounded-lg overflow-hidden border border-gray-700 group';
                
                card.innerHTML = `
                    <div class="relative h-48 overflow-hidden">
                        <img src="${car.image}" alt="${car.name}" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110 opacity-90 group-hover:opacity-100" onerror="this.src='https://placehold.co/600x400/1a1a1a/d4af37?text=Black+Cars'">
                        <div class="absolute top-0 right-0 bg-[#d4af37] text-black text-xs font-bold px-3 py-1 uppercase">
                            ${getCategoryName(car.category)}
                        </div>
                    </div>
                    
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-white mb-1 serif-font">${car.name}</h3>
                        <p class="text-[#d4af37] text-xs uppercase tracking-widest mb-4">Black Cars Collection</p>
                        
                        <div class="grid grid-cols-4 gap-2 text-gray-400 text-xs mb-6 border-b border-gray-700 pb-4">
                            <div class="text-center flex flex-col items-center gap-1">
                                <i class="fas fa-chair"></i>
                                <span>${car.specs.seats}</span>
                            </div>
                            <div class="text-center flex flex-col items-center gap-1">
                                <i class="fas fa-cogs"></i>
                                <span>${car.specs.trans}</span>
                            </div>
                            <div class="text-center flex flex-col items-center gap-1">
                                <i class="fas fa-gas-pump"></i>
                                <span>${car.specs.fuel}</span>
                            </div>
                            <div class="text-center flex flex-col items-center gap-1">
                                <i class="fas fa-tachometer-alt"></i>
                                <span>${car.specs.hp}</span>
                            </div>
                        </div>
                        
                        <div class="flex justify-between items-center">
                            <div>
                                <span class="text-2xl font-bold text-white">${car.price}€</span>
                                <span class="text-gray-500 text-xs">/dia</span>
                            </div>
                            <button onclick="openModal('${car.name}')" class="border border-white text-white px-4 py-2 text-xs font-bold uppercase hover:bg-white hover:text-black transition-colors rounded-sm">
                                Reservar
                            </button>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        function getCategoryName(cat) {
            switch(cat) {
                case 'sport': return 'Desportivo';
                case 'suv': return 'SUV Premium';
                case 'luxury': return 'Executivo';
                default: return 'Premium';
            }
        }

        // Filters
        function filterCars(category) {
            // Update buttons
            document.querySelectorAll('.filter-btn').forEach(btn => {
                if(btn.dataset.filter === category) {
                    btn.classList.add('border-[#d4af37]', 'text-[#d4af37]');
                    btn.classList.remove('border-gray-700', 'text-gray-400');
                } else {
                    btn.classList.remove('border-[#d4af37]', 'text-[#d4af37]');
                    btn.classList.add('border-gray-700', 'text-gray-400');
                }
            });
            renderCars(category);
        }

        // Modal Functions
        function openModal(carName) {
            document.getElementById('modalCarName').innerText = carName;
            document.getElementById('bookingModal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('bookingModal').classList.add('hidden');
        }

        function submitBooking() {
            closeModal();
            const toast = document.getElementById('toast');
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }
        
        // Mobile Menu
        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        // Close modal when clicking outside
        window.onclick = function(event) {
            const modal = document.getElementById('bookingModal');
            if (event.target == modal) {
                closeModal();
            }
        }

        // Init
        renderCars();

    </script>
</body>
</html>
