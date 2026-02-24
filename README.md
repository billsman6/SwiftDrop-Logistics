# SwiftDrop-Logistics
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SwiftDrop - Premium Delivery Services</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        'display': ['Space Grotesk', 'sans-serif'],
                        'body': ['Inter', 'sans-serif'],
                    },
                    colors: {
                        'swift': {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            500: '#0ea5e9',
                            600: '#0284c7',
                            900: '#0c4a6e',
                        }
                    },
                    animation: {
                        'float': 'float 6s ease-in-out infinite',
                        'slide-up': 'slideUp 0.6s ease-out',
                        'pulse-slow': 'pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-20px)' },
                        },
                        slideUp: {
                            '0%': { transform: 'translateY(30px)', opacity: '0' },
                            '100%': { transform: 'translateY(0)', opacity: '1' },
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .glass-effect {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
        }
        .gradient-text {
            background: linear-gradient(135deg, #0ea5e9 0%, #6366f1 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero-pattern {
            background-image: radial-gradient(circle at 1px 1px, rgba(14, 165, 233, 0.15) 1px, transparent 0);
            background-size: 40px 40px;
        }
        .card-hover {
            transition: all 0.3s ease;
        }
        .card-hover:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        .tracking-line {
            background: linear-gradient(90deg, #0ea5e9 0%, #6366f1 100%);
            height: 4px;
            border-radius: 2px;
            transition: width 1s ease;
        }
    </style>
</head>
<body class="font-body bg-gray-50 overflow-x-hidden">

    <!-- Navigation -->
    <nav class="fixed w-full z-50 glass-effect border-b border-gray-200 transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex items-center space-x-2 cursor-pointer" onclick="window.scrollTo(0,0)">
                    <div class="w-10 h-10 bg-gradient-to-br from-swift-500 to-indigo-600 rounded-xl flex items-center justify-center text-white text-xl font-bold transform rotate-3 hover:rotate-6 transition-transform">
                        <i class="fas fa-shipping-fast"></i>
                    </div>
                    <span class="font-display font-bold text-2xl text-gray-900 tracking-tight">SwiftDrop</span>
                </div>
                
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#services" class="text-gray-600 hover:text-swift-600 font-medium transition-colors">Services</a>
                    <a href="#tracking" class="text-gray-600 hover:text-swift-600 font-medium transition-colors">Track Order</a>
                    <a href="#pricing" class="text-gray-600 hover:text-swift-600 font-medium transition-colors">Pricing</a>
                    <a href="#about" class="text-gray-600 hover:text-swift-600 font-medium transition-colors">About</a>
                    <button onclick="openBookingModal()" class="bg-gray-900 text-white px-6 py-2.5 rounded-full font-medium hover:bg-swift-600 transition-all transform hover:scale-105 shadow-lg">
                        Book Delivery
                    </button>
                </div>

                <button class="md:hidden text-gray-600 text-2xl" onclick="toggleMobileMenu()">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div id="mobileMenu" class="hidden md:hidden bg-white border-t border-gray-200 absolute w-full">
            <div class="px-4 pt-2 pb-6 space-y-2">
                <a href="#services" class="block px-3 py-2 text-gray-600 hover:bg-gray-50 rounded-lg">Services</a>
                <a href="#tracking" class="block px-3 py-2 text-gray-600 hover:bg-gray-50 rounded-lg">Track Order</a>
                <a href="#pricing" class="block px-3 py-2 text-gray-600 hover:bg-gray-50 rounded-lg">Pricing</a>
                <button onclick="openBookingModal()" class="w-full mt-4 bg-swift-600 text-white px-6 py-3 rounded-lg font-medium">Book Delivery</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative pt-32 pb-20 lg:pt-40 lg:pb-32 overflow-hidden hero-pattern">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid lg:grid-cols-2 gap-12 items-center">
                <div class="space-y-8 animate-slide-up">
                    <div class="inline-flex items-center px-4 py-2 rounded-full bg-swift-100 text-swift-600 text-sm font-semibold">
                        <span class="w-2 h-2 bg-swift-500 rounded-full mr-2 animate-pulse"></span>
                        Now serving 50+ cities worldwide
                    </div>
                    <h1 class="font-display text-5xl lg:text-7xl font-bold text-gray-900 leading-tight">
                        Delivering <span class="gradient-text">Tomorrow</span> Today
                    </h1>
                    <p class="text-xl text-gray-600 max-w-lg leading-relaxed">
                        Experience lightning-fast delivery with real-time tracking, secure handling, and eco-friendly logistics solutions for your business.
                    </p>
                    <div class="flex flex-col sm:flex-row gap-4">
                        <button onclick="openBookingModal()" class="bg-gray-900 text-white px-8 py-4 rounded-full font-semibold text-lg hover:bg-swift-600 transition-all transform hover:scale-105 shadow-xl flex items-center justify-center gap-2">
                            <span>Ship Now</span>
                            <i class="fas fa-arrow-right"></i>
                        </button>
                        <button onclick="document.getElementById('tracking').scrollIntoView({behavior: 'smooth'})" class="bg-white text-gray-900 border-2 border-gray-200 px-8 py-4 rounded-full font-semibold text-lg hover:border-swift-500 hover:text-swift-600 transition-all flex items-center justify-center gap-2">
                            <i class="fas fa-search"></i>
                            <span>Track Package</span>
                        </button>
                    </div>
                    <div class="flex items-center gap-8 pt-4">
                        <div class="flex -space-x-3">
                            <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&h=100&fit=crop" class="w-10 h-10 rounded-full border-2 border-white" alt="User">
                            <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&h=100&fit=crop" class="w-10 h-10 rounded-full border-2 border-white" alt="User">
                            <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=100&h=100&fit=crop" class="w-10 h-10 rounded-full border-2 border-white" alt="User">
                            <div class="w-10 h-10 rounded-full border-2 border-white bg-gray-100 flex items-center justify-center text-xs font-bold text-gray-600">+2k</div>
                        </div>
                        <div class="text-sm text-gray-600">
                            <div class="flex text-yellow-400 text-xs mb-1">
                                <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                            </div>
                            <p>Trusted by 10,000+ businesses</p>
                        </div>
                    </div>
                </div>
                <div class="relative lg:h-[600px] flex items-center justify-center">
                    <div class="absolute w-96 h-96 bg-swift-500 rounded-full mix-blend-multiply filter blur-3xl opacity-20 animate-pulse-slow"></div>
                    <div class="absolute w-96 h-96 bg-indigo-500 rounded-full mix-blend-multiply filter blur-3xl opacity-20 animate-pulse-slow" style="animation-delay: 2s; right: 0;"></div>
                    <img src="https://images.unsplash.com/photo-1586528116311-ad8dd3c8310d?w=800&h=600&fit=crop" alt="Delivery Truck" class="relative z-10 rounded-3xl shadow-2xl animate-float object-cover w-full max-w-lg">
                    
                    <!-- Floating Stats Card -->
                    <div class="absolute -bottom-6 -left-6 bg-white p-6 rounded-2xl shadow-xl z-20 animate-float" style="animation-delay: 1s;">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center text-green-600">
                                <i class="fas fa-check-circle text-xl"></i>
                            </div>
                            <div>
                                <p class="text-2xl font-bold text-gray-900">99.8%</p>
                                <p class="text-sm text-gray-500">On-time delivery</p>
                            </div>
                        </div>
                    </div>

                    <!-- Speed Card -->
                    <div class="absolute top-10 -right-6 bg-white p-4 rounded-2xl shadow-xl z-20 animate-float" style="animation-delay: 0.5s;">
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 bg-swift-100 rounded-full flex items-center justify-center text-swift-600">
                                <i class="fas fa-bolt"></i>
                            </div>
                            <div>
                                <p class="text-lg font-bold text-gray-900">2-Hour</p>
                                <p class="text-xs text-gray-500">Express delivery</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Tracking Section -->
    <section id="tracking" class="py-20 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
                <h2 class="font-display text-4xl font-bold text-gray-900 mb-4">Track Your Shipment</h2>
                <p class="text-gray-600">Enter your tracking number to get real-time updates</p>
            </div>
            
            <div class="bg-gray-50 p-8 rounded-3xl shadow-inner">
                <div class="flex gap-4 mb-8">
                    <input type="text" id="trackingInput" placeholder="Enter tracking number (e.g., SWF123456789)" 
                        class="flex-1 px-6 py-4 rounded-xl border-2 border-gray-200 focus:border-swift-500 focus:outline-none text-lg font-mono uppercase">
                    <button onclick="trackOrder()" class="bg-swift-600 text-white px-8 py-4 rounded-xl font-semibold hover:bg-swift-700 transition-colors flex items-center gap-2">
                        <i class="fas fa-search"></i>
                        Track
                    </button>
                </div>

                <!-- Tracking Result -->
                <div id="trackingResult" class="hidden space-y-6">
                    <div class="bg-white p-6 rounded-2xl border border-gray-200">
                        <div class="flex justify-between items-center mb-6">
                            <div>
                                <p class="text-sm text-gray-500 mb-1">Tracking Number</p>
                                <p class="text-2xl font-mono font-bold text-gray-900" id="displayTrackingNum">SWF123456789</p>
                            </div>
                            <div class="text-right">
                                <p class="text-sm text-gray-500 mb-1">Estimated Delivery</p>
                                <p class="text-xl font-bold text-green-600" id="deliveryDate">Today by 8:00 PM</p>
                            </div>
                        </div>
                        
                        <div class="relative">
                            <div class="absolute left-4 top-0 bottom-0 w-0.5 bg-gray-200"></div>
                            <div class="space-y-8" id="trackingTimeline">
                                <!-- Timeline items injected by JS -->
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="font-display text-4xl font-bold text-gray-900 mb-4">Our Services</h2>
                <p class="text-gray-600 max-w-2xl mx-auto">Comprehensive logistics solutions tailored to your needs, from same-day delivery to international freight.</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Service Cards -->
                <div class="bg-white p-8 rounded-3xl card-hover border border-gray-100">
                    <div class="w-14 h-14 bg-swift-100 rounded-2xl flex items-center justify-center text-swift-600 text-2xl mb-6">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3 class="font-display text-xl font-bold text-gray-900 mb-3">Express Delivery</h3>
                    <p class="text-gray-600 mb-4">Same-day and next-day delivery options for urgent shipments with guaranteed time slots.</p>
                    <a href="#" class="text-swift-600 font-semibold flex items-center gap-2 hover:gap-3 transition-all">
                        Learn more <i class="fas fa-arrow-right text-sm"></i>
                    </a>
                </div>

                <div class="bg-white p-8 rounded-3xl card-hover border border-gray-100">
                    <div class="w-14 h-14 bg-indigo-100 rounded-2xl flex items-center justify-center text-indigo-600 text-2xl mb-6">
                        <i class="fas fa-globe"></i>
                    </div>
                    <h3 class="font-display text-xl font-bold text-gray-900 mb-3">International Shipping</h3>
                    <p class="text-gray-600 mb-4">Global freight forwarding with customs clearance and end-to-end tracking.</p>
                    <a href="#" class="text-swift-600 font-semibold flex items-center gap-2 hover:gap-3 transition-all">
                        Learn more <i class="fas fa-arrow-right text-sm"></i>
                    </a>
                </div>

                <div class="bg-white p-8 rounded-3xl card-hover border border-gray-100">
                    <div class="w-14 h-14 bg-green-100 rounded-2xl flex items-center justify-center text-green-600 text-2xl mb-6">
                        <i class="fas fa-warehouse"></i>
                    </div>
                    <h3 class="font-display text-xl font-bold text-gray-900 mb-3">Warehousing</h3>
                    <p class="text-gray-600 mb-4">Climate-controlled storage with inventory management and fulfillment services.</p>
                    <a href="#" class="text-swift-600 font-semibold flex items-center gap-2 hover:gap-3 transition-all">
                        Learn more <i class="fas fa-arrow-right text-sm"></i>
                    </a>
                </div>

                <div class="bg-white p-8 rounded-3xl card-hover border border-gray-100">
                    <div class="w-14 h-14 bg-purple-100 rounded-2xl flex items-center justify-center text-purple-600 text-2xl mb-6">
                        <i class="fas fa-box-open"></i>
                    </div>
                    <h3 class="font-display text-xl font-bold text-gray-900 mb-3">Last Mile Delivery</h3>
                    <p class="text-gray-600 mb-4">Optimized final delivery with real-time updates and flexible recipient options.</p>
                    <a href="#" class="text-swift-600 font-semibold flex items-center gap-2 hover:gap-3 transition-all">
                        Learn more <i class="fas fa-arrow-right text-sm"></i>
                    </a>
                </div>

                <div class="bg-white p-8 rounded-3xl card-hover border border-gray-100">
                    <div class="w-14 h-14 bg-orange-100 rounded-2xl flex items-center justify-center text-orange-600 text-2xl mb-6">
                        <i class="fas fa-temperature-low"></i>
                    </div>
                    <h3 class="font-display text-xl font-bold text-gray-900 mb-3">Cold Chain</h3>
                    <p class="text-gray-600 mb-4">Temperature-controlled logistics for pharmaceuticals and perishable goods.</p>
                    <a href="#" class="text-swift-600 font-semibold flex items-center gap-2 hover:gap-3 transition-all">
                        Learn more <i class="fas fa-arrow-right text-sm"></i>
                    </a>
                </div>

                <div class="bg-white p-8 rounded-3xl card-hover border border-gray-100">
                    <div class="w-14 h-14 bg-pink-100 rounded-2xl flex items-center justify-center text-pink-600 text-2xl mb-6">
                        <i class="fas fa-truck-loading"></i>
                    </div>
                    <h3 class="font-display text-xl font-bold text-gray-900 mb-3">Freight Transport</h3>
                    <p class="text-gray-600 mb-4">Full truckload (FTL) and less-than-truckload (LTL) shipping solutions.</p>
                    <a href="#" class="text-swift-600 font-semibold flex items-center gap-2 hover:gap-3 transition-all">
                        Learn more <i class="fas fa-arrow-right text-sm"></i>
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="py-20 bg-gray-900 text-white relative overflow-hidden">
        <div class="absolute inset-0 opacity-20">
            <div class="absolute inset-0" style="background-image: radial-gradient(circle at 2px 2px, rgba(255,255,255,0.15) 1px, transparent 0); background-size: 40px 40px;"></div>
        </div>
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
                <div class="space-y-2">
                    <p class="text-4xl md:text-5xl font-display font-bold text-swift-400 counter" data-target="50">0</p>
                    <p class="text-gray-400">Cities Covered</p>
                </div>
                <div class="space-y-2">
                    <p class="text-4xl md:text-5xl font-display font-bold text-swift-400 counter" data-target="2">0</p>
                    <p class="text-gray-400">Million Deliveries</p>
                </div>
                <div class="space-y-2">
                    <p class="text-4xl md:text-5xl font-display font-bold text-swift-400 counter" data-target="99">0</p>
                    <p class="text-gray-400">% Satisfaction</p>
                </div>
                <div class="space-y-2">
                    <p class="text-4xl md:text-5xl font-display font-bold text-swift-400 counter" data-target="24">0</p>
                    <p class="text-gray-400">/7 Support</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Modal -->
    <div id="bookingModal" class="fixed inset-0 z-50 hidden overflow-y-auto" aria-labelledby="modal-title" role="dialog" aria-modal="true">
        <div class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
            <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity backdrop-blur-sm" onclick="closeBookingModal()"></div>
            <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
            <div class="inline-block align-bottom bg-white rounded-3xl text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg w-full">
                <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                    <div class="flex justify-between items-center mb-5">
                        <h3 class="text-2xl font-display font-bold text-gray-900" id="modal-title">Book a Delivery</h3>
                        <button onclick="closeBookingModal()" class="text-gray-400 hover:text-gray-600">
                            <i class="fas fa-times text-xl"></i>
                        </button>
                    </div>
                    <form id="bookingForm" class="space-y-4" onsubmit="submitBooking(event)">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1">Pickup Address</label>
                            <input type="text" required class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-swift-500 focus:border-transparent" placeholder="Enter pickup location">
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1">Delivery Address</label>
                            <input type="text" required class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-swift-500 focus:border-transparent" placeholder="Enter delivery location">
                        </div>
                        <div class="grid grid-cols-2 gap-4">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-1">Package Weight</label>
                                <select class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-swift-500 focus:border-transparent">
                                    <option>Under 1 kg</option>
                                    <option>1-5 kg</option>
                                    <option>5-10 kg</option>
                                    <option>Over 10 kg</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-1">Service Type</label>
                                <select class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-swift-500 focus:border-transparent">
                                    <option>Standard</option>
                                    <option>Express (+$10)</option>
                                    <option>Same Day (+$25)</option>
                                </select>
                            </div>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1">Contact Email</label>
                            <input type="email" required class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-swift-500 focus:border-transparent" placeholder="your@email.com">
                        </div>
                        <button type="submit" class="w-full bg-swift-600 text-white py-3 rounded-lg font-semibold hover:bg-swift-700 transition-colors mt-6">
                            Get Quote & Book
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-12 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid md:grid-cols-4 gap-8 mb-8">
                <div class="space-y-4">
                    <div class="flex items-center space-x-2">
                        <div class="w-8 h-8 bg-gradient-to-br from-swift-500 to-indigo-600 rounded-lg flex items-center justify-center text-white">
                            <i class="fas fa-shipping-fast text-sm"></i>
                        </div>
                        <span class="font-display font-bold text-xl text-white">SwiftDrop</span>
                    </div>
                    <p class="text-sm">Revolutionizing logistics with technology-driven delivery solutions for businesses of all sizes.</p>
                    <div class="flex space-x-4">
                        <a href="#" class="w-8 h-8 rounded-full bg-gray-800 flex items-center justify-center hover:bg-swift-600 transition-colors"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="w-8 h-8 rounded-full bg-gray-800 flex items-center justify-center hover:bg-swift-600 transition-colors"><i class="fab fa-linkedin"></i></a>
                        <a href="#" class="w-8 h-8 rounded-full bg-gray-800 flex items-center justify-center hover:bg-swift-600 transition-colors"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div>
                    <h4 class="text-white font-semibold mb-4">Services</h4>
                    <ul class="space-y-2 text-sm">
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Express Delivery</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">International</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Warehousing</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Enterprise</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-white font-semibold mb-4">Company</h4>
                    <ul class="space-y-2 text-sm">
                        <li><a href="#" class="hover:text-swift-400 transition-colors">About Us</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Careers</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Press</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Blog</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-white font-semibold mb-4">Support</h4>
                    <ul class="space-y-2 text-sm">
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Help Center</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Track Order</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Contact Us</a></li>
                        <li><a href="#" class="hover:text-swift-400 transition-colors">Privacy Policy</a></li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-800 pt-8 flex flex-col md:flex-row justify-between items-center">
                <p class="text-sm text-gray-500">&copy; 2026 SwiftDrop Logistics. All rights reserved.</p>
                <div class="flex space-x-6 mt-4 md:mt-0 text-sm text-gray-500">
                    <a href="#" class="hover:text-white transition-colors">Terms</a>
                    <a href="#" class="hover:text-white transition-colors">Privacy</a>
                    <a href="#" class="hover:text-white transition-colors">Cookies</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('shadow-md');
            } else {
                navbar.classList.remove('shadow-md');
            }
        });

        // Mobile menu toggle
        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        // Booking Modal
        function openBookingModal() {
            document.getElementById('bookingModal').classList.remove('hidden');
            document.body.style.overflow = 'hidden';
        }

        function closeBookingModal() {
            document.getElementById('bookingModal').classList.add('hidden');
            document.body.style.overflow = 'auto';
        }

        function submitBooking(e) {
            e.preventDefault();
            const btn = e.target.querySelector('button[type="submit"]');
            const originalText = btn.innerText;
            btn.innerText = 'Processing...';
            btn.disabled = true;
            
            setTimeout(() => {
                btn.innerText = 'Booking Confirmed! ✓';
                btn.classList.remove('bg-swift-600');
                btn.classList.add('bg-green-600');
                
                setTimeout(() => {
                    closeBookingModal();
                    btn.innerText = originalText;
                    btn.disabled = false;
                    btn.classList.remove('bg-green-600');
                    btn.classList.add('bg-swift-600');
                    e.target.reset();
                    alert('Thank you! Your delivery has been scheduled. Check your email for confirmation.');
                }, 1000);
            }, 1500);
        }

        // Tracking Simulation
        function trackOrder() {
            const input = document.getElementById('trackingInput');
            const result = document.getElementById('trackingResult');
            const trackingNum = input.value.trim() || 'SWF' + Math.floor(Math.random() * 1000000000);
            
            if (!input.value.trim()) {
                input.value = trackingNum;
            }

            document.getElementById('displayTrackingNum').textContent = trackingNum.toUpperCase();
            
            // Simulate loading
            result.classList.remove('hidden');
            result.innerHTML = '<div class="text-center py-8"><i class="fas fa-spinner fa-spin text-3xl text-swift-600"></i><p class="mt-2 text-gray-600">Loading tracking information...</p></div>';
            
            setTimeout(() => {
                const statuses = [
                    { icon: 'fa-check-circle', color: 'text-green-500', title: 'Delivered', desc: 'Package delivered to recipient', time: '2:30 PM Today', active: true },
                    { icon: 'fa-truck', color: 'text-swift-600', title: 'Out for Delivery', desc: 'Courier is on the way', time: '8:15 AM Today', active: false },
                    { icon: 'fa-building', color: 'text-gray-400', title: 'Arrived at Facility', desc: 'Regional distribution center', time: '6:45 AM Today', active: false },
                    { icon: 'fa-box', color: 'text-gray-400', title: 'Picked Up', desc: 'Package collected from sender', time: 'Yesterday, 4:20 PM', active: false }
                ];

                let html = `
                    <div class="bg-white p-6 rounded-2xl border border-gray-200 animate-slide-up">
                        <div class="flex justify-between items-center mb-6">
                            <div>
                                <p class="text-sm text-gray-500 mb-1">Tracking Number</p>
                                <p class="text-2xl font-mono font-bold text-gray-900">${trackingNum.toUpperCase()}</p>
                            </div>
                            <div class="text-right">
                                <p class="text-sm text-gray-500 mb-1">Estimated Delivery</p>
                                <p class="text-xl font-bold text-green-600">Delivered</p>
                            </div>
                        </div>
                        <div class="relative">
                            <div class="absolute left-4 top-0 bottom-0 w-0.5 bg-gray-200"></div>
                            <div class="space-y-8">
                `;

                statuses.forEach((status, index) => {
                    html += `
                        <div class="relative flex items-start">
                            <div class="absolute left-0 w-8 h-8 rounded-full bg-white border-2 ${status.active ? 'border-green-500' : 'border-gray-300'} flex items-center justify-center z-10">
                                <i class="fas ${status.icon} ${status.color} text-sm"></i>
                            </div>
                            <div class="ml-12 flex-1">
                                <div class="flex justify-between items-start">
                                    <div>
                                        <h4 class="font-semibold text-gray-900 ${status.active ? 'text-lg' : ''}">${status.title}</h4>
                                        <p class="text-sm text-gray-500">${status.desc}</p>
                                    </div>
                                    <span class="text-sm text-gray-400 font-mono">${status.time}</span>
                                </div>
                            </div>
                        </div>
                    `;
                });

                html += `
                            </div>
                        </div>
                        <div class="mt-6 pt-6 border-t border-gray-200 flex justify-between items-center">
                            <div class="flex items-center gap-2 text-sm text-gray-600">
                                <i class="fas fa-map-marker-alt text-swift-600"></i>
                                <span>Delivered to: 123 Business Ave, Suite 100</span>
                            </div>
                            <button onclick="alert('Proof of delivery photo downloaded')" class="text-swift-600 hover:text-swift-700 font-medium text-sm">
                                <i class="fas fa-camera mr-1"></i> View POD
                            </button>
                        </div>
                    </div>
                `;

                result.innerHTML = html;
            }, 1500);
        }

        // Animated counters
        const observerOptions = {
            threshold: 0.5
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const counters = entry.target.querySelectorAll('.counter');
                    counters.forEach(counter => {
                        const target = parseInt(counter.getAttribute('data-target'));
                        const duration = 2000;
                        const step = target / (duration / 16);
                        let current = 0;
                        
                        const timer = setInterval(() => {
                            current += step;
                            if (current >= target) {
                                counter.textContent = target + (target === 2 ? 'M+' : target === 99 ? '%' : target === 24 ? '/7' : '+');
                                clearInterval(timer);
                            } else {
                                counter.textContent = Math.floor(current);
                            }
                        }, 16);
                    });
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.counter').forEach(counter => {
            observer.observe(counter.parentElement.parentElement);
        });

        // Enter key for tracking
        document.getElementById('trackingInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                trackOrder();
            }
        });
    </script>
</body>
</html>
2707 W Avenue 30, Los Angeles, CA 90065
