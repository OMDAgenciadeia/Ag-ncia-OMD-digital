<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OMD Digital - Agência de IA para WhatsApp e Redes Sociais</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --neon-blue: #00f2ff;
            --neon-lilac: #bc13fe;
            --dark-bg: #0f0f1a;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--dark-bg);
            color: white;
            overflow-x: hidden;
            padding-top: 80px; /* Espaço para a navbar fixa */
        }
        
        .neon-text-blue {
            color: var(--neon-blue);
            text-shadow: 0 0 10px rgba(0, 242, 255, 0.7);
        }
        
        .neon-text-lilac {
            color: var(--neon-lilac);
            text-shadow: 0 0 10px rgba(188, 19, 254, 0.7);
        }
        
        .neon-border-blue {
            border: 2px solid var(--neon-blue);
            box-shadow: 0 0 15px rgba(0, 242, 255, 0.5);
        }
        
        .neon-border-lilac {
            border: 2px solid var(--neon-lilac);
            box-shadow: 0 0 15px rgba(188, 19, 254, 0.5);
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, var(--neon-blue) 0%, var(--neon-lilac) 100%);
        }
        
        .hero-section {
            background: linear-gradient(rgba(15, 15, 26, 0.9), rgba(15, 15, 26, 0.9)),
                         url('https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
        }
        
        .client-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 25px rgba(0, 242, 255, 0.3), 0 10px 25px rgba(188, 19, 254, 0.3);
        }
        
        .glow-hover:hover {
            box-shadow: 0 0 20px rgba(0, 242, 255, 0.7), 0 0 20px rgba(188, 19, 254, 0.7);
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .pulse-animation {
            animation: pulse 3s infinite;
        }
        
        /* Carrossel */
        .carousel {
            position: relative;
            width: 100%;
            height: 500px;
            overflow: hidden;
        }
        
        .carousel-slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 1s ease-in-out;
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .carousel-slide.active {
            opacity: 1;
        }
        
        .carousel-content {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 2rem;
            border-radius: 15px;
            max-width: 800px;
            text-align: center;
        }
        
        .carousel-indicators {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
        }
        
        .carousel-indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .carousel-indicator.active {
            background-color: var(--neon-blue);
        }
        
        .carousel-nav {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 10;
            font-size: 1.5rem;
        }
        
        .carousel-prev {
            left: 20px;
        }
        
        .carousel-next {
            right: 20px;
        }
        
        .fixed-nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
        }
    </style>
</head>
<body>
    <!-- Navbar Fixa -->
    <nav class="fixed-nav bg-black bg-opacity-90 backdrop-blur-md shadow-lg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <div class="flex items-center">
                    <div class="flex-shrink-0">
                        <span class="text-2xl font-bold neon-text-blue">OMD</span>
                        <span class="text-2xl font-bold neon-text-lilac">Digital</span>
                    </div>
                </div>
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-8">
                        <a href="#home" class="text-white hover:text-neon-blue px-3 py-2 rounded-md text-sm font-medium">Home</a>
                        <a href="#servicos" class="text-white hover:text-neon-lilac px-3 py-2 rounded-md text-sm font-medium">Serviços</a>
                        <a href="#sobre" class="text-white hover:text-neon-blue px-3 py-2 rounded-md text-sm font-medium">Sobre Nós</a>
                        <a href="#clientes" class="text-white hover:text-neon-lilac px-3 py-2 rounded-md text-sm font-medium">Clientes</a>
                        <a href="#contato" class="text-white hover:text-neon-blue px-3 py-2 rounded-md text-sm font-medium">Contato</a>
                    </div>
                </div>
                <div class="md:hidden">
                    <button class="text-white focus:outline-none">
                        <i class="fas fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Carrossel -->
    <div class="carousel">
        <!-- Slide 1 -->
        <div class="carousel-slide active" style="background-image: url('https://images.unsplash.com/photo-1551434678-e076c223a692?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');">
            <div class="carousel-content">
                <h2 class="text-4xl font-bold mb-4 neon-text-blue">Transforme Seu WhatsApp em uma Máquina de Vendas!</h2>
                <p class="text-xl mb-6">Empresas que adotaram nossa solução de IA para WhatsApp registraram aumento de até 70% nas vendas.</p>
                <a href="#servicos" class="gradient-bg text-black font-bold py-3 px-8 rounded-full inline-block hover:opacity-90">Saiba Mais</a>
            </div>
        </div>
                
        <!-- Slide 2 -->
        <div class="carousel-slide" style="background-image: url('https://images.unsplash.com/photo-1521791136064-7986c2920216?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80');">
            <div class="carousel-content">
                <h2 class="text-4xl font-bold mb-4 neon-text-lilac">Atendimento 24/7 com Inteligência Artificial</h2>
                <p class="text-xl mb-6">Nossa IA trabalha enquanto você dorme, respondendo clientes e gerando oportunidades de negócio a qualquer hora.</p>
                <a href="#servicos" class="gradient-bg text-black font-bold py-3 px-8 rounded-full inline-block hover:opacity-90">Conheça Nossos Planos</a>
            </div>
        </div>
                
        <!-- Slide 3 -->
        <div class="carousel-slide" style="background-image: url('https://images.unsplash.com/photo-1600267165477-6d19ccd502a1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');">
            <div class="carousel-content">
                <h2 class="text-4xl font-bold mb-4 neon-text-blue">Clientes Satisfeitos em Todo o Brasil</h2>
                <p class="text-xl mb-6">Mais de 500 empresas já transformaram seus resultados com nossas soluções tecnológicas.</p>
                <a href="#clientes" class="gradient-bg text-black font-bold py-3 px-8 rounded-full inline-block hover:opacity-90">Veja Depoimentos</a>
            </div>
        </div>
                
        <!-- Botões de navegação -->
        <button class="carousel-nav carousel-prev">
            <i class="fas fa-chevron-left"></i>
        </button>
        <button class="carousel-nav carousel-next">
            <i class="fas fa-chevron-right"></i>
        </button>
                
        <!-- Indicadores -->
        <div class="carousel-indicators">
            <div class="carousel-indicator active" data-slide="0"></div>
            <div class="carousel-indicator" data-slide="1"></div>
            <div class="carousel-indicator" data-slide="2"></div>
        </div>
    </div>

    <!-- Hero Section -->
    <section id="home" class="hero-section min-h-screen flex items-center pt-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
                <div>
                    <h1 class="text-4xl md:text-6xl font-bold mb-6">
                        <span class="neon-text-blue">Venda 24H</span>
                        <span class="neon-text-lilac">no WhatsApp</span>
                        com IA
                    </h1>
                    <p class="text-lg text-gray-300 mb-8">
                        Transforme seu WhatsApp em uma máquina de vendas inteligente que trabalha para você 
                        dia e noite, atendendo clientes e gerando resultados em qualquer nicho de mercado.
                    </p>
                    <div class="flex flex-wrap gap-4">
                        <a href="https://dash.superagentes.ai/@omdigital" target="_blank" class="gradient-bg text-black font-bold py-3 px-8 rounded-full hover:opacity-90 transition duration-300 transform hover:scale-105">
                            Fale Conosco
                        </a>
                        <a href="#servicos" class="neon-border-lilac text-white font-bold py-3 px-8 rounded-full hover:bg-purple-900 hover:bg-opacity-20 transition duration-300 transform hover:scale-105">
                            Nossos Serviços
                        </a>
                    </div>
                </div>
                <div class="relative">
                    <div class="relative z-10 rounded-xl overflow-hidden neon-border-blue pulse-animation">
                        <img src="https://images.unsplash.com/photo-1521791136064-7986c2920216?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80"
                              alt="Empresário feliz com vendas no WhatsApp"
                              class="w-full h-auto object-cover">
                    </div>
                    <div class="absolute -bottom-6 -right-6 w-32 h-32 rounded-full gradient-bg opacity-70"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="py-16 bg-black bg-opacity-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
                <div class="p-6 rounded-xl bg-gray-900 bg-opacity-50 neon-border-blue">
                    <div class="text-4xl font-bold neon-text-blue mb-2">7+</div>
                    <div class="text-gray-300">Anos no mercado</div>
                </div>
                <div class="p-6 rounded-xl bg-gray-900 bg-opacity-50 neon-border-lilac">
                    <div class="text-4xl font-bold neon-text-lilac mb-2">500+</div>
                    <div class="text-gray-300">Clientes atendidos</div>
                </div>
                <div class="p-6 rounded-xl bg-gray-900 bg-opacity-50 neon-border-blue">
                    <div class="text-4xl font-bold neon-text-blue mb-2">24/7</div>
                    <div class="text-gray-300">Vendas automáticas</div>
                </div>
                <div class="p-6 rounded-xl bg-gray-900 bg-opacity-50 neon-border-lilac">
                    <div class="text-4xl font-bold neon-text-lilac mb-2">10+</div>
                    <div class="text-gray-300">Países atendidos</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Serviços Section -->
    <section id="servicos" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-5xl font-bold mb-4">
                    <span class="neon-text-blue">Nossos</span>
                    <span class="neon-text-lilac">Serviços</span>
                </h2>
                <p class="text-xl text-gray-300 max-w-3xl mx-auto">
                    Soluções completas para alavancar seu negócio no digital
                </p>
            </div>
                        
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Serviço 1 -->
                <div class="bg-gray-900 bg-opacity-50 rounded-xl p-8 neon-border-blue hover:neon-border-lilac transition duration-500 client-card">
                    <div class="text-5xl neon-text-blue mb-6">
                        <i class="fab fa-whatsapp"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-4">Automação WhatsApp</h3>
                    <p class="text-gray-300 mb-6">
                        Soluções completas de automação para WhatsApp Business com IA, incluindo chatbots inteligentes, fluxos de atendimento e integração com CRMs.
                    </p>
                    <ul class="space-y-2 text-gray-300">
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-blue mr-2"></i>
                            Chatbots 24/7 com IA
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-blue mr-2"></i>
                            Atendimento multicanal
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-blue mr-2"></i>
                            Integração com API oficial
                        </li>
                    </ul>
                </div>
                                
                <!-- Serviço 2 -->
                <div class="bg-gray-900 bg-opacity-50 rounded-xl p-8 neon-border-lilac hover:neon-border-blue transition duration-500 client-card">
                    <div class="text-5xl neon-text-lilac mb-6">
                        <i class="fas fa-robot"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-4">IA Personalizada</h3>
                    <p class="text-gray-300 mb-6">
                        Desenvolvemos uma IA exclusiva para sua marca, totalmente personalizada para atender às necessidades específicas do seu negócio.
                    </p>
                    <ul class="space-y-2 text-gray-300">
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-lilac mr-2"></i>
                            IA sob medida para sua empresa
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-lilac mr-2"></i>
                            Processamento de áudio inteligente
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-lilac mr-2"></i>
                            Entendimento de intenção em mensagens
                        </li>
                    </ul>
                </div>
                                
                <!-- Serviço 3 -->
                <div class="bg-gray-900 bg-opacity-50 rounded-xl p-8 neon-border-blue hover:neon-border-lilac transition duration-500 client-card">
                    <div class="text-5xl neon-text-blue mb-6">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-4">Consultoria WhatsApp</h3>
                    <p class="text-gray-300 mb-6">
                        Estratégias personalizadas para implementação e otimização de WhatsApp Business em diferentes modelos de negócio.
                    </p>
                    <ul class="space-y-2 text-gray-300">
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-blue mr-2"></i>
                            Diagnóstico de fluxos
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-blue mr-2"></i>
                            Estratégias de conversão
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle neon-text-blue mr-2"></i>
                            Métricas e analytics
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Video Section -->
    <section class="py-20 bg-black bg-opacity-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-5xl font-bold mb-4">
                    <span class="neon-text-lilac">Como a IA</span>
                    <span class="neon-text-blue">Transforma Seu WhatsApp</span>
                </h2>
                <p class="text-xl text-gray-300 max-w-3xl mx-auto">
                    Veja na prática como nossa solução funciona para diferentes negócios
                </p>
            </div>
                        
            <div class="aspect-w-16 aspect-h-9 rounded-xl overflow-hidden neon-border-blue glow-hover max-w-4xl mx-auto">
                <iframe class="w-full h-96" src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>
    </section>

    <!-- Sobre Nós Section -->
    <section id="sobre" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
                <div class="relative">
                    <div class="relative z-10 rounded-xl overflow-hidden neon-border-lilac">
                        <img src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80"
                              alt="Equipe OMD Digital"
                              class="w-full h-auto object-cover">
                    </div>
                    <div class="absolute -top-6 -left-6 w-32 h-32 rounded-full gradient-bg opacity-70"></div>
                </div>
                <div>
                    <h2 class="text-3xl md:text-5xl font-bold mb-6">
                        <span class="neon-text-blue">7 Anos</span>
                        <span class="neon-text-lilac">Transformando Negócios</span>
                    </h2>
                    <p class="text-lg text-gray-300 mb-6">
                        Desde 2016, a OMD Digital vem revolucionando a forma como empresas se comunicam e vendem 
                        no ambiente digital. Começamos como especialistas em marketing tradicional e evoluímos 
                        para nos tornarmos referência em inteligência artificial aplicada ao WhatsApp.
                    </p>
                    <p class="text-lg text-gray-300 mb-6">
                        Nossa missão é democratizar o acesso à tecnologia de ponta, permitindo que empresas de 
                        todos os tamanhos e segmentos possam competir em igualdade com os grandes players.
                    </p>
                    <div class="flex flex-wrap gap-4">
                        <div class="p-4 rounded-lg bg-gray-900 bg-opacity-50 neon-border-blue">
                            <div class="text-xl font-bold neon-text-blue mb-1">Missão</div>
                            <div class="text-gray-300">Transformar comunicação em vendas</div>
                        </div>
                        <div class="p-4 rounded-lg bg-gray-900 bg-opacity-50 neon-border-lilac">
                            <div class="text-xl font-bold neon-text-lilac mb-1">Visão</div>
                            <div class="text-gray-300">Ser líder em IA para WhatsApp</div>
                        </div>
                        <div class="p-4 rounded-lg bg-gray-900 bg-opacity-50 neon-border-blue">
                            <div class="text-xl font-bold neon-text-blue mb-1">Valores</div>
                            <div class="text-gray-300">Inovação, Resultados, Ética</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Clientes Section -->
    <section id="clientes" class="py-20 bg-black bg-opacity-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-5xl font-bold mb-4">
                    <span class="neon-text-lilac">Clientes</span>
                    <span class="neon-text-blue">Satisfeitos</span>
                </h2>
                <p class="text-xl text-gray-300 max-w-3xl mx-auto">
                    Empresários de diversos nichos que transformaram seus resultados com a OMD
                </p>
            </div>
                        
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Cliente 1 - Médico -->
                <div class="bg-gray-900 bg-opacity-50 rounded-xl overflow-hidden neon-border-blue client-card transition duration-500">
                    <img src="https://images.unsplash.com/photo-1622253692010-333f2da6031d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2128&q=80"
                          alt="Médico feliz"
                          class="w-full h-64 object-cover">
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-2">Dr. Carlos Silva</h3>
                        <p class="text-gray-300 mb-4">Clínica Médica - São Paulo</p>
                        <p class="text-gray-300 italic">
                            "A OMD implementou um chatbot no WhatsApp que agenda consultas 24 horas por dia. 
                            Nossas vagas passaram a ser preenchidas 3x mais rápido!"
                        </p>
                    </div>
                </div>
                                
                <!-- Cliente 2 - Dentista -->
                <div class="bg-gray-900 bg-opacity-50 rounded-xl overflow-hidden neon-border-lilac client-card transition duration-500">
                    <img src="https://images.unsplash.com/photo-1559839734-2b71ea197ec2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80"
                          alt="Dentista feliz"
                          class="w-full h-64 object-cover">
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-2">Dra. Ana Oliveira</h3>
                        <p class="text-gray-300 mb-4">Odontologia Estética - Rio de Janeiro</p>
                        <p class="text-gray-300 italic">
                            "Com a IA da OMD, conseguimos triar pacientes, enviar lembretes de consulta e 
                            oferecer planos de tratamento automaticamente. Faturamento +40% em 3 meses!"
                        </p>
                    </div>
                </div>
                                
                <!-- Cliente 3 - Hamburgueria -->
                <div class="bg-gray-900 bg-opacity-50 rounded-xl overflow-hidden neon-border-blue client-card transition duration-500">
                    <img src="https://images.unsplash.com/photo-1600891964599-f61ba0e24092?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80"
                          alt="Dono de hamburgueria feliz"
                          class="w-full h-64 object-cover">
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-2">Ricardo Mendes</h3>
                        <p class="text-gray-300 mb-4">Burger King - Porto Alegre</p>
                        <p class="text-gray-300 italic">
                            "O WhatsApp automatizado da OMD recebe pedidos, envia cardápios e promoções. 
                            Reduzimos 70% do tempo da equipe no atendimento e aumentamos as vendas em 60%."
                        </p>
                    </div>
                </div>
            </div>
                        
            <div class="mt-12 text-center">
                <a href="https://dash.superagentes.ai/@omdigital" target="_blank" class="gradient-bg text-black font-bold py-3 px-8 rounded-full hover:opacity-90 transition duration-300 inline-block transform hover:scale-105">
                    Quero Resultados Também
                </a>
            </div>
        </div>
    </section>

    <!-- Diferenciais Section -->
    <section class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-5xl font-bold mb-4">
                    <span class="neon-text-blue">Por que</span>
                    <span class="neon-text-lilac">Escolher a OMD</span>
                </h2>
                <p class="text-xl text-gray-300 max-w-3xl mx-auto">
                    Nossos diferenciais que fazem a diferença no seu negócio
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-gray-900 bg-opacity-50 p-8 rounded-xl neon-border-blue client-card">
                    <div class="text-4xl neon-text-blue mb-4">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-4">Implementação Rápida</h3>
                    <p class="text-gray-300">
                        Em apenas 72 horas seu WhatsApp estará vendendo automaticamente 24 horas por dia.
                    </p>
                </div>
                
                <div class="bg-gray-900 bg-opacity-50 p-8 rounded-xl neon-border-lilac client-card">
                    <div class="text-4xl neon-text-lilac mb-4">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-4">Segurança Garantida</h3>
                    <p class="text-gray-300">
                        Utilizamos a API oficial do WhatsApp com todas as certificações e compliance necessários.
                    </p>
                </div>
                
                <div class="bg-gray-900 bg-opacity-50 p-8 rounded-xl neon-border-blue client-card">
                    <div class="text-4xl neon-text-blue mb-4">
                        <i class="fas fa-headset"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-4">Suporte Especializado</h3>
                    <p class="text-gray-300">
                        Equipe técnica disponível para tirar dúvidas e fazer ajustes sempre que necessário.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const carousel = document.querySelector('.carousel');
            const slides = document.querySelectorAll('.carousel-slide');
            const indicators = document.querySelectorAll('.carousel-indicator');
            const prevBtn = document.querySelector('.carousel-prev');
            const nextBtn = document.querySelector('.carousel-next');
            
            let currentIndex = 0;
            const slideCount = slides.length;
            let intervalId;
            
            // Function to show slide
            function showSlide(index) {
                slides.forEach(slide => slide.classList.remove('active'));
                indicators.forEach(indicator => indicator.classList.remove('active'));
                
                slides[index].classList.add('active');
                indicators[index].classList.add('active');
                currentIndex = index;
            }
            
            // Function for next slide
            function nextSlide() {
                let newIndex = (currentIndex + 1) % slideCount;
                showSlide(newIndex);
            }
            
            // Function for previous slide
            function prevSlide() {
                let newIndex = (currentIndex - 1 + slideCount) % slideCount;
                showSlide(newIndex);
            }
            
            // Start auto rotation
            function startAutoRotation() {
                intervalId = setInterval(nextSlide, 5000); // Change slide every 5 seconds
            }
            
            // Stop auto rotation
            function stopAutoRotation() {
                clearInterval(intervalId);
            }
            
            // Event listeners
            nextBtn.addEventListener('click', () => {
                nextSlide();
                stopAutoRotation();
                startAutoRotation();
            });
            
            prevBtn.addEventListener('click', () => {
                prevSlide();
                stopAutoRotation();
                startAutoRotation();
            });
            
            indicators.forEach((indicator, index) => {
                indicator.addEventListener('click', () => {
                    showSlide(index);
                    stopAutoRotation();
                    startAutoRotation();
                });
            });
            
            // Pause on hover
            carousel.addEventListener('mouseenter', stopAutoRotation);
            carousel.addEventListener('mouseleave', startAutoRotation);
            
            // Initialize
            showSlide(0);
            startAutoRotation();
        });
    </script>
</body>
</html>

