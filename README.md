<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>URBAN KIN | UBK - Streetwear 2026</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700;900&family=Rubik+Wet+Paint&display=swap" rel="stylesheet">
    
    <!-- FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        ubk: {
                            gold: '#D4AF37', 
                            dark: '#0f0f0f',
                            gray: '#1a1a1a',
                            light: '#e5e5e5',
                            accent: '#f59e0b'
                        }
                    },
                    fontFamily: {
                        graffiti: ['"Rubik Wet Paint"', 'cursive'],
                        sans: ['"Montserrat"', 'sans-serif'],
                    },
                    backgroundImage: {
                        // FONDO DE INICIO
                        'hero-pattern': "url('FOTOS/Gemini_Generated_Image_9v5gd09v5gd09v5g-Photoroom.png')",
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #0f0f0f;
            color: #e5e5e5;
            overflow-x: hidden;
        }

        /* Texto Graffiti con borde */
        .text-outline {
            -webkit-text-stroke: 1px #fff;
            color: transparent; 
        }
        
        /* Efectos visuales */
        .card-shadow:hover {
            box-shadow: 0 0 25px rgba(212, 175, 55, 0.4);
            transform: translateY(-5px);
        }

        /* Animaciones */
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .fade-in-element {
            animation: fadeInUp 0.6s ease-out forwards;
        }

        .shirt-container {
            position: relative;
            height: 320px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            background: radial-gradient(circle at center, #2a2a2a 0%, #000000 100%);
        }
        
        .shirt-img {
            transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            filter: drop-shadow(0 10px 10px rgba(0,0,0,0.5));
            width: 100%;
            height: 100%;
            object-fit: contain; /* Ajusta la imagen para que se vea completa */
        }
        
        .product-card:hover .shirt-img {
            transform: scale(1.05);
        }

        /* Hero Overlay Gradient */
        .hero-overlay {
            background: linear-gradient(to bottom, rgba(0,0,0,0.3) 0%, rgba(0,0,0,0.5) 60%, #0f0f0f 100%);
        }

        /* Modal Overlay */
        .modal-overlay {
            backdrop-filter: blur(8px);
            background-color: rgba(0, 0, 0, 0.85);
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0f0f0f; 
        }
        ::-webkit-scrollbar-thumb {
            background: #D4AF37; 
            border-radius: 4px;
        }
    </style>
</head>
<body class="font-sans antialiased">

    <!-- Navbar -->
    <nav id="navbar" class="fixed w-full z-50 transition-all duration-300 bg-black/60 backdrop-blur-md border-b border-white/10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-24">
                <div class="flex-shrink-0 cursor-pointer group" onclick="window.scrollTo(0,0)">
                    <h1 class="font-graffiti text-4xl text-ubk-gold tracking-wider group-hover:scale-105 transition-transform drop-shadow-lg">
                        <span class="text-white text-outline" style="-webkit-text-stroke: 1px #D4AF37;">URBAN</span> KIN
                    </h1>
                </div>
                
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-8">
                        <a href="#inicio" class="text-white hover:text-ubk-gold px-3 py-2 text-sm font-bold tracking-[0.2em] transition-colors drop-shadow-md">INICIO</a>
                        <a href="#catalogo" class="bg-ubk-gold text-black px-6 py-2 rounded-sm text-sm font-bold tracking-[0.2em] hover:bg-white hover:shadow-[0_0_15px_rgba(255,255,255,0.5)] transition-all shadow-lg">CATÁLOGO</a>
                        <a href="#quienes-somos" class="text-white hover:text-ubk-gold px-3 py-2 text-sm font-bold tracking-[0.2em] transition-colors drop-shadow-md">NOSOTROS</a>
                        <a href="#contacto" class="text-white hover:text-ubk-gold px-3 py-2 text-sm font-bold tracking-[0.2em] transition-colors drop-shadow-md">CONTACTO</a>
                    </div>
                </div>

                <div class="-mr-2 flex md:hidden">
                    <button type="button" onclick="toggleMenu()" class="text-ubk-gold hover:text-white p-2">
                        <i class="fas fa-bars text-3xl"></i>
                    </button>
                </div>
            </div>
        </div>
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-black border-t border-ubk-gold/30 absolute w-full">
            <div class="px-4 pt-4 pb-6 space-y-2">
                <a href="#inicio" onclick="toggleMenu()" class="text-white block px-3 py-3 font-bold border-b border-gray-800">INICIO</a>
                <a href="#catalogo" onclick="toggleMenu()" class="text-ubk-gold block px-3 py-3 font-bold border-b border-gray-800">CATÁLOGO</a>
                <a href="#quienes-somos" onclick="toggleMenu()" class="text-white block px-3 py-3 font-bold border-b border-gray-800">NOSOTROS</a>
                <a href="#contacto" onclick="toggleMenu()" class="text-white block px-3 py-3 font-bold">CONTACTO</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section (Inicio) -->
    <header id="inicio" class="relative h-screen flex items-center justify-center overflow-hidden">
        <!-- Background Image fixed -->
        <div class="absolute inset-0 bg-gray-900 bg-hero-pattern bg-cover bg-center bg-no-repeat bg-fixed transform scale-105"></div>
        
        <!-- Overlay Gradient -->
        <div class="absolute inset-0 hero-overlay"></div>

        <div class="relative z-10 text-center px-4 max-w-6xl mx-auto mt-20">
            <div class="inline-block border border-ubk-gold/50 bg-black/60 backdrop-blur-sm px-6 py-2 mb-6 rounded-full fade-in-element shadow-xl">
                <p class="text-ubk-gold font-bold tracking-[0.4em] text-xs md:text-sm">COLECCIÓN 2026 / VOL. 1</p>
            </div>
            
            <h2 class="font-graffiti text-7xl md:text-9xl text-white mb-4 drop-shadow-[0_5px_5px_rgba(0,0,0,0.8)] fade-in-element" style="animation-delay: 0.2s;">
                URBAN <span class="text-transparent bg-clip-text bg-gradient-to-b from-ubk-gold to-orange-600 drop-shadow-none">KIN</span>
            </h2>
            
            <p class="text-gray-100 text-lg md:text-2xl max-w-3xl mx-auto mb-12 font-light fade-in-element leading-relaxed drop-shadow-md" style="animation-delay: 0.4s;">
                El inicio de la revolución. <br>
                Diseños para quienes dominan el asfalto.
                <span class="text-ubk-gold font-bold block mt-2 text-shadow-sm">EST. 2026</span>
            </p>
            
            <div class="flex flex-col sm:flex-row justify-center gap-6 fade-in-element" style="animation-delay: 0.6s;">
                <a href="#catalogo" class="group relative px-8 py-4 bg-ubk-gold text-black font-black uppercase tracking-wider overflow-hidden shadow-lg hover:shadow-ubk-gold/50 transition-all">
                    <span class="relative z-10 group-hover:text-white transition-colors">Ver Lanzamiento Vol. 1</span>
                    <div class="absolute inset-0 bg-black transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left duration-300"></div>
                </a>
                <a href="#" onclick="openModal('workModal')" class="px-8 py-4 border-2 border-white bg-black/30 backdrop-blur-sm text-white font-bold uppercase tracking-wider hover:bg-white hover:text-black transition-all shadow-lg">
                    Trabaja con Nosotros
                </a>
            </div>
        </div>

        <!-- Scroll Indicator -->
        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce text-white/80 drop-shadow-md">
            <i class="fas fa-chevron-down text-2xl"></i>
        </div>
    </header>

    <!-- Sección Catálogo -->
    <section id="catalogo" class="relative py-24 bg-ubk-dark">
        <!-- Elements background decor -->
        <div class="absolute top-0 right-0 w-1/3 h-full bg-gradient-to-l from-ubk-gray to-transparent opacity-20 pointer-events-none"></div>

        <div class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="flex flex-col md:flex-row justify-between items-end mb-16 border-b border-gray-800 pb-6">
                <div>
                    <h3 class="font-graffiti text-5xl md:text-6xl text-white mb-2">
                        CATÁLOGO <span class="text-ubk-gold">2026</span>
                    </h3>
                    <p class="text-gray-400">Volumen 1 / Street Wear / Primera Edición</p>
                </div>
                <div class="hidden md:block text-right">
                    <p class="text-ubk-gold font-bold text-2xl" id="item-count">0 items</p>
                </div>
            </div>

            <!-- GRID DE PRODUCTOS (Se llena con JS) -->
            <div id="product-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
                <!-- Los productos se inyectan aquí -->
            </div>
            
            <!-- Botón Ver Más -->
            <div class="text-center mt-20" id="load-more-container">
                <button onclick="loadFullCatalog()" class="px-12 py-5 border border-ubk-gold text-ubk-gold font-bold tracking-widest hover:bg-ubk-gold hover:text-black transition-all duration-300 shadow-[0_0_20px_rgba(212,175,55,0.2)]">
                    VER CATÁLOGO COMPLETO <i class="fas fa-plus ml-2"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Sección Quiénes Somos -->
    <section id="quienes-somos" class="relative py-24 bg-black overflow-hidden">
        <div class="absolute inset-0 opacity-20 bg-[url('https://www.transparenttextures.com/patterns/carbon-fibre.png')]"></div>
        
        <div class="max-w-7xl mx-auto px-4 grid grid-cols-1 lg:grid-cols-2 gap-16 items-center relative z-10">
            <div class="relative group">
                <div class="absolute -inset-4 bg-ubk-gold opacity-20 blur-lg group-hover:opacity-40 transition-opacity"></div>
                <!-- Imagen de skaters locales -->
                <img src="FOTOS/WhatsApp Image 2026-02-02 at 17.01.44.jpeg" alt="Skater Team" class="relative w-full grayscale hover:grayscale-0 transition-all duration-700 shadow-2xl border-2 border-gray-800" onerror="this.src='https://images.unsplash.com/photo-1512353087810-25dfcd100962?q=80&w=1920&auto=format&fit=crop'">
                <!-- Floating badge -->
                <div class="absolute -bottom-6 -right-6 bg-ubk-gold text-black p-6 font-bold text-center shadow-lg hidden md:block">
                    <span class="block text-4xl font-black">EST.</span>
                    <span class="block text-xl">2026</span>
                </div>
            </div>
            
            <div>
                <h4 class="text-ubk-gold font-bold tracking-[0.5em] mb-4">NUESTRA HISTORIA</h4>
                <h3 class="font-graffiti text-5xl text-white mb-8">ORIGEN <span class="text-gray-500 line-through decoration-ubk-gold">2026</span></h3>
                <p class="text-gray-400 text-lg mb-6 leading-relaxed">
                    Este 2026 marca el inicio de una era. Urban Kin (UBK) surge como la respuesta a la monotonía. Somos la primera línea de defensa contra el estilo aburrido.
                </p>
                <p class="text-gray-400 text-lg mb-8 leading-relaxed">
                    Nuestra colección Volumen 1 es solo el principio. Únete a la familia ahora y sé parte de la historia desde el día uno.
                </p>
                <div class="grid grid-cols-2 gap-6">
                    <div class="bg-ubk-gray p-4 border-l-4 border-ubk-gold">
                        <i class="fas fa-shipping-fast text-2xl text-white mb-2"></i>
                        <h5 class="font-bold text-white">ENVÍOS 2026</h5>
                        <p class="text-xs text-gray-500">Logística renovada</p>
                    </div>
                    <div class="bg-ubk-gray p-4 border-l-4 border-ubk-gold">
                        <i class="fas fa-certificate text-2xl text-white mb-2"></i>
                        <h5 class="font-bold text-white">VOLUMEN 1</h5>
                        <p class="text-xs text-gray-500">Edición Fundadores</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contacto" class="bg-[#050505] border-t border-gray-900 pt-20 pb-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-12 mb-16">
                <!-- Col 1 -->
                <div>
                    <h2 class="font-graffiti text-4xl text-white mb-6">URBAN <span class="text-ubk-gold">KIN</span></h2>
                    <p class="text-gray-500 mb-6">
                        Establecidos en 2026. <br>
                        Diseño urbano sin compromisos.
                    </p>
                    <div class="flex space-x-4">
                        <a href="#" class="w-10 h-10 rounded-full bg-gray-800 flex items-center justify-center text-white hover:bg-ubk-gold hover:text-black transition-colors"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="w-10 h-10 rounded-full bg-gray-800 flex items-center justify-center text-white hover:bg-ubk-gold hover:text-black transition-colors"><i class="fab fa-tiktok"></i></a>
                    </div>
                </div>

                <!-- Col 2 -->
                <div class="md:pl-10">
                    <h4 class="text-white font-bold mb-6 tracking-widest">NAVEGACIÓN</h4>
                    <ul class="space-y-4 text-gray-500">
                        <li><a href="#catalogo" class="hover:text-ubk-gold transition-colors">Catálogo Vol. 1</a></li>
                        <li><button onclick="openModal('sizeModal')" class="hover:text-ubk-gold transition-colors text-left w-full">Tabla de Tallas</button></li>
                        <li><button onclick="openModal('trackingModal')" class="hover:text-ubk-gold transition-colors text-left w-full">Seguimiento de Orden</button></li>
                        <li><button onclick="openModal('workModal')" class="hover:text-ubk-gold transition-colors text-left w-full">Trabaja con Nosotros</button></li>
                    </ul>
                </div>

                <!-- Col 3 -->
                <div>
                    <h4 class="text-white font-bold mb-6 tracking-widest">CONTACTO CORPORATIVO</h4>
                    <div class="bg-gray-900 p-6 rounded-lg border border-gray-800">
                        <p class="text-gray-400 mb-4 text-sm">Compras por mayor y contacto directo.</p>
                        <a href="mailto:crew@urbankin.app" class="flex items-center gap-3 text-white hover:text-ubk-gold mb-3 transition-colors">
                            <i class="fas fa-envelope"></i> contacto2026@urbankin.app
                        </a>
                        <button onclick="openModal('workModal')" class="w-full mt-4 bg-ubk-gold text-black font-bold text-xs py-2 uppercase hover:bg-white transition-colors">
                            Zona Mayoristas
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="text-center border-t border-gray-900 pt-8">
                <p class="text-gray-600 text-sm">© 2026 URBAN KIN. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <!-- MODALES -->

    <!-- Modal Tallas -->
    <div id="sizeModal" class="fixed inset-0 z-[60] hidden">
        <div class="absolute inset-0 modal-overlay" onclick="closeModal('sizeModal')"></div>
        <div class="relative bg-ubk-gray border border-ubk-gold/30 p-8 max-w-lg w-full mx-4 shadow-2xl rounded-sm fade-in-element">
            <button onclick="closeModal('sizeModal')" class="absolute top-4 right-4 text-gray-500 hover:text-white"><i class="fas fa-times text-xl"></i></button>
            
            <h3 class="font-graffiti text-3xl text-ubk-gold mb-6 text-center">GUÍA DE TALLAS (CM)</h3>
            <p class="text-gray-400 text-center text-xs mb-6 uppercase tracking-widest">Corte Oversize 2026 Standard</p>
            
            <div class="overflow-x-auto">
                <table class="w-full text-sm text-left text-gray-400">
                    <thead class="text-xs text-ubk-gold uppercase bg-black/50">
                        <tr>
                            <th class="px-6 py-3">Talla</th>
                            <th class="px-6 py-3">Ancho (Pecho)</th>
                            <th class="px-6 py-3">Largo</th>
                            <th class="px-6 py-3">Manga</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr class="border-b border-gray-800 hover:bg-gray-800">
                            <td class="px-6 py-4 font-bold text-white">S</td>
                            <td class="px-6 py-4">54</td>
                            <td class="px-6 py-4">72</td>
                            <td class="px-6 py-4">22</td>
                        </tr>
                        <tr class="border-b border-gray-800 hover:bg-gray-800">
                            <td class="px-6 py-4 font-bold text-white">M</td>
                            <td class="px-6 py-4">57</td>
                            <td class="px-6 py-4">74</td>
                            <td class="px-6 py-4">23</td>
                        </tr>
                        <tr class="border-b border-gray-800 hover:bg-gray-800">
                            <td class="px-6 py-4 font-bold text-white">L</td>
                            <td class="px-6 py-4">60</td>
                            <td class="px-6 py-4">76</td>
                            <td class="px-6 py-4">24</td>
                        </tr>
                        <tr class="hover:bg-gray-800">
                            <td class="px-6 py-4 font-bold text-white">XL</td>
                            <td class="px-6 py-4">63</td>
                            <td class="px-6 py-4">78</td>
                            <td class="px-6 py-4">25</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- Modal Tracking -->
    <div id="trackingModal" class="fixed inset-0 z-[60] hidden">
        <div class="absolute inset-0 modal-overlay" onclick="closeModal('trackingModal')"></div>
        <div class="relative bg-ubk-gray border border-ubk-gold/30 p-8 max-w-md w-full mx-4 shadow-2xl rounded-sm fade-in-element flex flex-col items-center">
            <button onclick="closeModal('trackingModal')" class="absolute top-4 right-4 text-gray-500 hover:text-white"><i class="fas fa-times text-xl"></i></button>
            
            <i class="fas fa-shipping-fast text-5xl text-ubk-gold mb-4"></i>
            <h3 class="font-bold text-2xl text-white mb-2">RASTREA TU ORDEN</h3>
            <p class="text-gray-400 text-center text-sm mb-6">Ingresa tu código de pedido UBK-2026</p>
            
            <form onsubmit="trackOrder(event)" class="w-full">
                <input type="text" placeholder="Ej: UBK-8821X" class="w-full bg-black border border-gray-700 text-white px-4 py-3 mb-4 focus:outline-none focus:border-ubk-gold tracking-widest text-center uppercase" required>
                <button type="submit" class="w-full bg-ubk-gold text-black font-bold py-3 uppercase hover:bg-white transition-colors">
                    BUSCAR PAQUETE
                </button>
            </form>
            
            <div id="tracking-result" class="hidden mt-6 bg-black/50 p-4 w-full border-l-2 border-green-500">
                <p class="text-green-500 font-bold text-sm">EN TRÁNSITO</p>
                <p class="text-gray-300 text-xs mt-1">Tu pedido está en el centro de distribución central. <br>Fecha estimada: 48hrs.</p>
            </div>
        </div>
    </div>

    <!-- Modal Trabajo / Mayorista -->
    <div id="workModal" class="fixed inset-0 z-[60] hidden">
        <div class="absolute inset-0 modal-overlay" onclick="closeModal('workModal')"></div>
        <div class="relative bg-ubk-gray border border-ubk-gold/30 p-8 max-w-2xl w-full mx-4 shadow-2xl rounded-sm fade-in-element">
            <button onclick="closeModal('workModal')" class="absolute top-4 right-4 text-gray-500 hover:text-white"><i class="fas fa-times text-xl"></i></button>
            
            <div class="text-center mb-8">
                <h3 class="font-graffiti text-3xl text-white">UBK CREW & <span class="text-ubk-gold">PARTNERS</span></h3>
                <p class="text-gray-400 mt-2">Únete al equipo o vende UBK en tu tienda.</p>
            </div>

            <form onsubmit="submitWorkForm(event)" class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div class="col-span-1">
                    <label class="block text-ubk-gold text-xs font-bold mb-2">NOMBRE COMPLETO</label>
                    <input type="text" class="w-full bg-black border border-gray-700 text-white px-3 py-2 focus:outline-none focus:border-ubk-gold" required>
                </div>
                <div class="col-span-1">
                    <label class="block text-ubk-gold text-xs font-bold mb-2">EMAIL</label>
                    <input type="email" class="w-full bg-black border border-gray-700 text-white px-3 py-2 focus:outline-none focus:border-ubk-gold" required>
                </div>
                <div class="col-span-1 md:col-span-2">
                    <label class="block text-ubk-gold text-xs font-bold mb-2">INTERÉS</label>
                    <select class="w-full bg-black border border-gray-700 text-white px-3 py-2 focus:outline-none focus:border-ubk-gold appearance-none">
                        <option>Compra Mayorista / Distribución</option>
                        <option>Trabajar en UBK (Diseñador/Ventas)</option>
                        <option>Colaboración Artística</option>
                        <option>Otro</option>
                    </select>
                </div>
                <div class="col-span-1 md:col-span-2">
                    <label class="block text-ubk-gold text-xs font-bold mb-2">MENSAJE / PROPUESTA</label>
                    <textarea rows="4" class="w-full bg-black border border-gray-700 text-white px-3 py-2 focus:outline-none focus:border-ubk-gold" placeholder="Cuéntanos tu idea..."></textarea>
                </div>
                <div class="col-span-1 md:col-span-2 mt-2">
                    <button type="submit" class="w-full bg-white text-black font-black py-3 uppercase hover:bg-ubk-gold transition-colors">
                        ENVIAR SOLICITUD
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- Botón Whatsapp Flotante -->
    <a href="#" class="fixed bottom-8 right-8 bg-[#25D366] hover:bg-[#1faa53] text-white p-4 rounded-full shadow-[0_0_20px_rgba(37,211,102,0.5)] transition-all z-50 hover:scale-110 flex items-center justify-center w-14 h-14">
        <i class="fab fa-whatsapp text-3xl"></i>
    </a>

    <!-- Toast Notification -->
    <div id="toast" class="fixed bottom-10 left-1/2 transform -translate-x-1/2 bg-white text-black px-8 py-4 shadow-2xl z-[70] translate-y-40 transition-all duration-300 flex items-center gap-4 border-l-4 border-ubk-gold">
        <i class="fas fa-check-circle text-green-600 text-xl"></i>
        <div>
            <h4 class="font-bold uppercase text-sm" id="toast-title">Carrito Actualizado</h4>
            <span id="toast-message" class="text-sm text-gray-600">Producto agregado</span>
        </div>
    </div>

    <script>
        // --- CONFIGURACIÓN 2026 ---
        // Asignamos tus imágenes locales a cada producto
        const designs = [
    { 
        name: "Snoopy Fly Away", 
        price: 58,
        images: {
            black: { front: "FOTOS/SNOOPY1BF.jpg", back: "FOTOS/SNOOPY1BB.jpg" },
            white: { front: "FOTOS/SNOOPY1WF.jpg", back: "FOTOS/SNOOPY1WB.jpg" }
        }
    },
    // Asegúrate de actualizar los nombres de los archivos según como los guardaste
];

        function createProductCard(design, index) {
    const pId = `prod-${index}`;
    return `
        <div class="product-card group bg-ubk-gray rounded-sm overflow-hidden border border-gray-800 hover:border-ubk-gold transition-all duration-300 relative card-shadow">
            
            <div class="flex h-64 bg-black border-b border-gray-800">
                <div class="w-1/2 border-r border-gray-900 p-2 flex items-center justify-center bg-[#111]">
                    <img id="${pId}-front" src="${design.images.black.front}" class="max-h-full object-contain transition-opacity duration-300" alt="Frente">
                </div>
                <div class="w-1/2 p-2 flex items-center justify-center bg-[#111]">
                    <img id="${pId}-back" src="${design.images.black.back}" class="max-h-full object-contain transition-opacity duration-300" alt="Espalda">
                </div>
            </div>

            <div class="p-5 bg-[#151515]">
                <div class="flex justify-between items-start mb-4">
                    <h4 class="font-bold text-white uppercase tracking-tighter">${design.name}</h4>
                    <span class="text-ubk-gold font-black">$${design.price}</span>
                </div>
                
                <div class="flex gap-4 mb-5">
                    <button onclick="updateColor('${pId}', 'black', ${index})" class="w-8 h-8 rounded-full bg-black border-2 border-ubk-gold active:scale-90 transition-transform shadow-lg"></button>
                    <button onclick="updateColor('${pId}', 'white', ${index})" class="w-8 h-8 rounded-full bg-white border-2 border-gray-600 active:scale-90 transition-transform shadow-lg"></button>
                </div>

                <button onclick="addToCart('${design.name}')" class="w-full py-3 bg-ubk-gold text-black font-bold text-xs uppercase hover:bg-white transition-colors">
                    AGREGAR AL CARRITO
                </button>
            </div>
        </div>
    `;
} 

        function initCatalog() {
            const grid = document.getElementById('product-grid');
            const initialProducts = designs.slice(0, 6); 
            grid.innerHTML = initialProducts.map((d, i) => createProductCard(d, i)).join('');
            document.getElementById('item-count').innerText = `Mostrando 6 de ${designs.length}`;
        }

        function loadFullCatalog() {
            const grid = document.getElementById('product-grid');
            const buttonContainer = document.getElementById('load-more-container');
            const currentCount = grid.children.length;
            const remainingProducts = designs.slice(currentCount);
            
            if (remainingProducts.length === 0) return;

            const newHtml = remainingProducts.map((d, i) => createProductCard(d, i + currentCount)).join('');
            grid.insertAdjacentHTML('beforeend', newHtml);
            document.getElementById('item-count').innerText = `Mostrando ${designs.length} de ${designs.length}`;
            buttonContainer.innerHTML = '<p class="text-gray-500 italic mt-8">Colección Vol. 1 Completamente Cargada.</p>';
        }

        // --- SISTEMA DE MODALES Y FORMULARIOS ---

        function openModal(modalId) {
            document.getElementById(modalId).classList.remove('hidden');
            document.getElementById(modalId).classList.add('flex');
        }

        function closeModal(modalId) {
            document.getElementById(modalId).classList.add('hidden');
            document.getElementById(modalId).classList.remove('flex');
            // Reset forms if needed
            if(modalId === 'trackingModal') {
                document.getElementById('tracking-result').classList.add('hidden');
                document.querySelector('#trackingModal form').reset();
            }
        }

        function trackOrder(e) {
            e.preventDefault();
            const btn = e.target.querySelector('button');
            const originalText = btn.innerText;
            btn.innerText = 'BUSCANDO...';
            
            setTimeout(() => {
                document.getElementById('tracking-result').classList.remove('hidden');
                btn.innerText = originalText;
            }, 1000);
        }

        function submitWorkForm(e) {
            e.preventDefault();
            closeModal('workModal');
            showToast('Solicitud Enviada', 'El equipo de UBK te contactará pronto.');
            e.target.reset();
        }

        // --- UTILIDADES GLOBALES ---
        
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('bg-black/95', 'shadow-lg', 'py-0');
                navbar.classList.remove('h-24');
            } else {
                navbar.classList.remove('bg-black/95', 'shadow-lg', 'py-0');
                navbar.classList.add('h-24');
            }
        });

        function toggleMenu() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
        }

        function addToCart(name) {
            showToast('Carrito Actualizado', `${name} añadido al Vol. 1 Bag.`);
        }

        function showToast(title, message) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-title').innerText = title;
            document.getElementById('toast-message').innerText = message;
            
            toast.classList.remove('translate-y-40');
            setTimeout(() => {
                toast.classList.add('translate-y-40');
            }, 3000);
        }

        // Iniciar
        initCatalog();

    function updateColor(pId, color, idx) {
    const d = designs[idx];
    const front = document.getElementById(`${pId}-front`);
    const back = document.getElementById(`${pId}-back`);
    
    // Cambiamos las rutas
    front.src = d.images[color].front;
    back.src = d.images[color].back;
    
    // Pequeño efecto de parpadeo al cambiar
    [front, back].forEach(img => {
        img.style.opacity = '0.5';
        setTimeout(() => img.style.opacity = '1', 150);
    });
}
</script>
</body>
</html>