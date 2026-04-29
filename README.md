<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <meta name="description" content="Daily Tools Nest - Your one-stop platform for free online tools. QR Code Generator, Unit Converter, Text Tools, Password Generator and more. Fast, free, and easy to use.">
    <meta name="keywords" content="online tools, QR code generator, unit converter, text tools, password generator, free tools, daily tools nest">
    <meta name="author" content="Daily Tools Nest">
    <meta name="robots" content="index, follow">
    
    <!-- Open Graph Tags -->
    <meta property="og:title" content="Daily Tools Nest - Free Online Tools Collection">
    <meta property="og:description" content="Your one-stop platform for free online tools. QR Code Generator, Unit Converter, Text Tools, and more coming soon. No signup required.">
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://dailytoolsnest.com">
    <meta property="og:image" content="https://dailytoolsnest.com/og-image.jpg">
    
    <!-- Twitter Card Tags -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Daily Tools Nest - Free Online Tools Collection">
    <meta name="twitter:description" content="Your one-stop platform for free online tools. No signup, no watermark, completely free.">
    
    <title>Daily Tools Nest - Free Online Tools for Everyday Tasks</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- QR Code Library -->
    <script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            transition: background-color 0.3s ease, color 0.3s ease;
        }
        
        /* Dark mode styles */
        body.dark-mode {
            background-color: #111827;
            color: #F9FAFB;
        }
        
        body.dark-mode .bg-white {
            background-color: #1F2937 !important;
        }
        
        body.dark-mode .bg-gray-50 {
            background-color: #111827 !important;
        }
        
        body.dark-mode .text-gray-600,
        body.dark-mode .text-gray-500,
        body.dark-mode .text-gray-700 {
            color: #D1D5DB !important;
        }
        
        body.dark-mode .border-gray-200,
        body.dark-mode .border-gray-300 {
            border-color: #374151 !important;
        }
        
        body.dark-mode .hover\:bg-gray-50:hover {
            background-color: #374151 !important;
        }
        
        body.dark-mode .bg-gray-100 {
            background-color: #374151 !important;
        }
        
        /* Ad container styling */
        .ad-container {
            min-height: 250px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%);
            border-radius: 12px;
            text-align: center;
            border: 2px dashed #3B82F6;
        }
        
        body.dark-mode .ad-container {
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
            border-color: #3B82F6;
        }
        
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        
        ::-webkit-scrollbar-thumb {
            background: #3B82F6;
            border-radius: 4px;
        }
        
        /* Loading animation */
        .loader {
            border: 3px solid #f3f3f3;
            border-top: 3px solid #3B82F6;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            display: inline-block;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Tool card hover effects */
        .tool-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .tool-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        
        /* Gradient text */
        .gradient-text {
            background: linear-gradient(135deg, #3B82F6 0%, #8B5CF6 100%);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        /* Countdown timer */
        .countdown-timer {
            font-family: monospace;
            font-size: 1.5rem;
            font-weight: bold;
            color: #3B82F6;
        }
        
        /* Responsive ads */
        @media (max-width: 768px) {
            .ad-container {
                min-height: 200px;
            }
        }
        
        /* Smooth transitions */
        .page-transition {
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Header -->
    <header class="bg-white shadow-lg sticky top-0 z-50 transition-colors duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center space-x-2">
                    <i class="fas fa-tools text-2xl text-blue-600"></i>
                    <a href="#home" class="text-xl font-bold gradient-text">Daily Tools Nest</a>
                </div>
                
                <!-- Desktop Navigation -->
                <div class="hidden md:flex space-x-8">
                    <a href="#home" class="text-gray-700 hover:text-blue-600 transition">Home</a>
                    <a href="#tools" class="text-gray-700 hover:text-blue-600 transition">Tools</a>
                    <a href="#blog" class="text-gray-700 hover:text-blue-600 transition">Blog</a>
                    <a href="#contact" class="text-gray-700 hover:text-blue-600 transition">Contact</a>
                </div>
                
                <div class="flex items-center space-x-4">
                    <button id="darkModeToggle" class="p-2 rounded-lg bg-gray-100 hover:bg-gray-200 transition">
                        <i class="fas fa-moon"></i>
                    </button>
                    <button id="mobileMenuBtn" class="md:hidden p-2 rounded-lg bg-gray-100">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </div>
            
            <!-- Mobile Navigation -->
            <div id="mobileMenu" class="hidden md:hidden pb-4 page-transition">
                <div class="flex flex-col space-y-3">
                    <a href="#home" class="text-gray-700 hover:text-blue-600 transition py-2">Home</a>
                    <a href="#tools" class="text-gray-700 hover:text-blue-600 transition py-2">Tools</a>
                    <a href="#blog" class="text-gray-700 hover:text-blue-600 transition py-2">Blog</a>
                    <a href="#contact" class="text-gray-700 hover:text-blue-600 transition py-2">Contact</a>
                </div>
            </div>
        </div>
    </header>

    <main id="mainContent" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <!-- Hero Section -->
        <section id="home" class="text-center mb-12 page-transition">
            <h1 class="text-4xl md:text-5xl font-bold mb-4">
                Free Online Tools for 
                <span class="gradient-text">Everyday Tasks</span>
            </h1>
            <p class="text-xl text-gray-600 mb-8 max-w-3xl mx-auto">
                Professional tools that work instantly in your browser. No signup, no watermark, completely free.
            </p>
            
            <!-- Search Bar -->
            <div class="max-w-2xl mx-auto relative">
                <i class="fas fa-search absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400"></i>
                <input type="text" id="searchTools" placeholder="Search tools by name or category..." 
                       class="w-full px-12 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent">
            </div>
            
            <div class="mt-6">
                <a href="#tools" class="inline-flex items-center space-x-2 bg-blue-600 text-white px-6 py-3 rounded-xl hover:bg-blue-700 transition">
                    <span>Explore All Tools</span>
                    <i class="fas fa-arrow-right"></i>
                </a>
            </div>
        </section>

        <!-- Top Ad Banner -->
        <div class="ad-container mb-8" data-ad-slot="728x90_top">
            <div class="text-gray-600 dark:text-gray-300">
                <i class="fas fa-ad"></i> Advertisement (728x90) - Adstera Space
            </div>
        </div>

        <!-- Stats Section -->
        <div class="grid grid-cols-2 md:grid-cols-3 gap-6 mb-12">
            <div class="bg-white rounded-xl p-6 text-center shadow-md transition-colors duration-300">
                <i class="fas fa-tools fa-2x text-blue-600 mb-2"></i>
                <div class="text-2xl font-bold" id="toolsCount">1</div>
                <div class="text-gray-600">Active Tools</div>
            </div>
            <div class="bg-white rounded-xl p-6 text-center shadow-md transition-colors duration-300">
                <i class="fas fa-chart-line fa-2x text-green-600 mb-2"></i>
                <div class="text-2xl font-bold" id="todayUsage">0</div>
                <div class="text-gray-600">Today's Usage</div>
            </div>
            <div class="bg-white rounded-xl p-6 text-center shadow-md transition-colors duration-300">
                <i class="fas fa-users fa-2x text-purple-600 mb-2"></i>
                <div class="text-2xl font-bold">10,000+</div>
                <div class="text-gray-600">Happy Users</div>
            </div>
        </div>

        <!-- Tools Grid Section -->
        <section id="tools" class="mb-12">
            <h2 class="text-3xl font-bold mb-8 text-center gradient-text">Our Tools</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6" id="toolsGrid">
                <!-- QR Code Generator (Active Tool) -->
                <div class="tool-card bg-white rounded-xl shadow-md overflow-hidden cursor-pointer transition-colors duration-300" data-tool="qr">
                    <div class="p-6">
                        <div class="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mb-4 mx-auto">
                            <i class="fas fa-qrcode fa-2x text-blue-600"></i>
                        </div>
                        <h3 class="text-xl font-bold text-center mb-2">QR Code Generator</h3>
                        <p class="text-gray-600 text-center text-sm mb-3">Create custom QR codes with logos and colors</p>
                        <div class="inline-block bg-green-100 text-green-700 px-2 py-1 rounded-full text-xs mx-auto block w-fit">Active</div>
                    </div>
                    <div class="bg-gray-50 p-3 text-center">
                        <button onclick="showTool('qr')" class="text-blue-600 font-semibold">Use Tool →</button>
                    </div>
                </div>

                <!-- Unit Converter (Coming in 2 weeks) -->
                <div class="tool-card bg-white rounded-xl shadow-md overflow-hidden transition-colors duration-300">
                    <div class="p-6">
                        <div class="w-16 h-16 bg-gray-100 rounded-full flex items-center justify-center mb-4 mx-auto">
                            <i class="fas fa-ruler-combined fa-2x text-gray-600"></i>
                        </div>
                        <h3 class="text-xl font-bold text-center mb-2">Unit Converter</h3>
                        <p class="text-gray-600 text-center text-sm mb-3">Convert length, weight, temperature, and more</p>
                        <div class="inline-block bg-amber-100 text-amber-700 px-2 py-1 rounded-full text-xs mx-auto block w-fit">Coming in 2 weeks</div>
                    </div>
                    <div class="bg-gray-50 p-3 text-center">
                        <button onclick="showComingSoon('unit', 14)" class="text-amber-600 font-semibold">Notify Me →</button>
                    </div>
                </div>

                <!-- Text Case Converter (Coming in 4 weeks) -->
                <div class="tool-card bg-white rounded-xl shadow-md overflow-hidden transition-colors duration-300">
                    <div class="p-6">
                        <div class="w-16 h-16 bg-gray-100 rounded-full flex items-center justify-center mb-4 mx-auto">
                            <i class="fas fa-text-height fa-2x text-gray-600"></i>
                        </div>
                        <h3 class="text-xl font-bold text-center mb-2">Text Case Converter</h3>
                        <p class="text-gray-600 text-center text-sm mb-3">Convert text to uppercase, lowercase, title case</p>
                        <div class="inline-block bg-amber-100 text-amber-700 px-2 py-1 rounded-full text-xs mx-auto block w-fit">Coming in 4 weeks</div>
                    </div>
                    <div class="bg-gray-50 p-3 text-center">
                        <button onclick="showComingSoon('text', 28)" class="text-amber-600 font-semibold">Notify Me →</button>
                    </div>
                </div>

                <!-- Password Generator (Coming in 6 weeks) -->
                <div class="tool-card bg-white rounded-xl shadow-md overflow-hidden transition-colors duration-300">
                    <div class="p-6">
                        <div class="w-16 h-16 bg-gray-100 rounded-full flex items-center justify-center mb-4 mx-auto">
                            <i class="fas fa-key fa-2x text-gray-600"></i>
                        </div>
                        <h3 class="text-xl font-bold text-center mb-2">Password Generator</h3>
                        <p class="text-gray-600 text-center text-sm mb-3">Generate secure, random passwords instantly</p>
                        <div class="inline-block bg-amber-100 text-amber-700 px-2 py-1 rounded-full text-xs mx-auto block w-fit">Coming in 6 weeks</div>
                    </div>
                    <div class="bg-gray-50 p-3 text-center">
                        <button onclick="showComingSoon('password', 42)" class="text-amber-600 font-semibold">Notify Me →</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- QR Code Generator Tool Interface (Hidden by default) -->
        <div id="qrToolInterface" class="hidden page-transition">
            <button onclick="hideTool()" class="mb-4 text-blue-600 hover:text-blue-700">
                <i class="fas fa-arrow-left"></i> Back to All Tools
            </button>
            
            <div class="bg-white rounded-2xl shadow-xl p-6 md:p-8 transition-colors duration-300">
                <h2 class="text-3xl font-bold mb-2 text-center gradient-text">QR Code Generator</h2>
                <p class="text-center text-gray-600 mb-6">Create custom QR codes with colors, logos, and high-quality downloads</p>
                
                <div class="grid lg:grid-cols-2 gap-8">
                    <!-- Input Form -->
                    <div class="space-y-4">
                        <div>
                            <label class="block text-sm font-medium mb-2">QR Code Type</label>
                            <select id="qrType" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                                <option value="url">URL / Website</option>
                                <option value="text">Plain Text</option>
                                <option value="email">Email</option>
                                <option value="phone">Phone Number</option>
                                <option value="sms">SMS</option>
                                <option value="wifi">WiFi Network</option>
                            </select>
                        </div>
                        
                        <div id="dynamicInput">
                            <label class="block text-sm font-medium mb-2">Enter URL</label>
                            <input type="text" id="qrValue" placeholder="https://example.com" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium mb-2">Foreground Color</label>
                            <input type="color" id="fgColor" value="#000000" class="w-full h-10 rounded-lg cursor-pointer">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium mb-2">Background Color</label>
                            <input type="color" id="bgColor" value="#FFFFFF" class="w-full h-10 rounded-lg cursor-pointer">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium mb-2">Size (px)</label>
                            <select id="size" class="w-full px-4 py-2 border border-gray-300 rounded-lg">
                                <option value="200">200x200</option>
                                <option value="300">300x300</option>
                                <option value="400">400x400</option>
                                <option value="500">500x500</option>
                                <option value="800" selected>800x800</option>
                            </select>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium mb-2">Error Correction</label>
                            <select id="errorCorrection" class="w-full px-4 py-2 border border-gray-300 rounded-lg">
                                <option value="L">L - 7%</option>
                                <option value="M" selected>M - 15%</option>
                                <option value="Q">Q - 25%</option>
                                <option value="H">H - 30%</option>
                            </select>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium mb-2">Logo (Optional)</label>
                            <input type="file" id="logoUpload" accept="image/png,image/jpeg" class="w-full px-4 py-2 border border-gray-300 rounded-lg">
                            <p class="text-xs text-gray-500 mt-1">Max 100kb, PNG or JPG (Logo appears in center)</p>
                        </div>
                        
                        <button id="generateBtn" class="w-full bg-blue-600 text-white py-3 rounded-lg font-semibold hover:bg-blue-700 transition">
                            Generate QR Code
                        </button>
                    </div>
                    
                    <!-- Output Area -->
                    <div class="space-y-6">
                        <div class="bg-gray-50 rounded-xl p-6 text-center transition-colors duration-300">
                            <div id="qrcode" class="flex justify-center items-center min-h-[300px]">
                                <div class="text-gray-400">Generate your QR code above</div>
                            </div>
                        </div>
                        
                        <div class="grid grid-cols-2 gap-3">
                            <button id="downloadPNG" class="bg-green-500 text-white py-2 rounded-lg hover:bg-green-600 transition">
                                <i class="fas fa-download"></i> PNG
                            </button>
                            <button id="downloadSVG" class="bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600 transition">
                                <i class="fas fa-download"></i> SVG
                            </button>
                            <button id="copyClipboard" class="bg-purple-500 text-white py-2 rounded-lg hover:bg-purple-600 transition">
                                <i class="fas fa-copy"></i> Copy Image
                            </button>
                            <button id="printQR" class="bg-gray-500 text-white py-2 rounded-lg hover:bg-gray-600 transition">
                                <i class="fas fa-print"></i> Print
                            </button>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium mb-2">Embed Code</label>
                            <textarea id="embedCode" rows="2" class="w-full px-4 py-2 border border-gray-300 rounded-lg font-mono text-sm" readonly></textarea>
                            <button id="copyEmbed" class="mt-2 text-sm text-blue-600 hover:text-blue-700">Copy Code</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Sidebar ad for tool page -->
            <div class="ad-container mt-8" data-ad-slot="300x250_tool_sidebar">
                <div class="text-gray-600 dark:text-gray-300">Advertisement (300x250) - Adsterra Space</div>
            </div>
        </div>

        <!-- Coming Soon Modal (Hidden by default) -->
        <div id="comingSoonModal" class="hidden fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center p-4">
            <div class="bg-white rounded-2xl p-6 max-w-md w-full page-transition">
                <div class="text-center">
                    <i class="fas fa-tools fa-3x text-amber-500 mb-4"></i>
                    <h3 class="text-2xl font-bold mb-2">Coming Soon!</h3>
                    <p class="text-gray-600 mb-4" id="modalToolName">This tool is under development</p>
                    <div id="countdownDisplay" class="countdown-timer mb-4"></div>
                    <p class="text-sm text-gray-500 mb-4">Get notified when this tool launches:</p>
                    <form id="notifyForm" class="space-y-3" onsubmit="return false;">
                        <input type="email" id="notifyEmail" placeholder="Your email address" required class="w-full px-4 py-2 border border-gray-300 rounded-lg">
                        <button type="submit" class="w-full bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition">
                            Notify Me
                        </button>
                    </form>
                    <button onclick="closeModal()" class="mt-4 text-gray-500 hover:text-gray-700">Close</button>
                </div>
            </div>
        </div>

        <!-- Blog Section -->
        <section id="blog" class="mb-12">
            <h2 class="text-3xl font-bold mb-8 text-center gradient-text">Latest from Our Blog</h2>
            <div class="grid md:grid-cols-3 gap-6" id="blogPosts"></div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="bg-white rounded-2xl shadow-xl p-8 mb-12 transition-colors duration-300">
            <h2 class="text-3xl font-bold mb-6 text-center gradient-text">Get in Touch</h2>
            <div class="max-w-2xl mx-auto">
                <form id="contactForm" onsubmit="return false;">
                    <div class="grid md:grid-cols-2 gap-4 mb-4">
                        <input type="text" placeholder="Your Name" required class="w-full px-4 py-2 border border-gray-300 rounded-lg">
                        <input type="email" placeholder="Your Email" required class="w-full px-4 py-2 border border-gray-300 rounded-lg">
                    </div>
                    <input type="text" placeholder="Subject" required class="w-full px-4 py-2 border border-gray-300 rounded-lg mb-4">
                    <textarea rows="5" placeholder="Your Message" required class="w-full px-4 py-2 border border-gray-300 rounded-lg mb-4"></textarea>
                    <button type="submit" class="w-full bg-blue-600 text-white py-3 rounded-lg font-semibold hover:bg-blue-700 transition">
                        Send Message
                    </button>
                    <p id="contactMessage" class="text-sm text-center mt-3 text-green-600 hidden"></p>
                </form>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <h3 class="text-xl font-bold mb-4 flex items-center space-x-2">
                        <i class="fas fa-tools"></i>
                        <span>Daily Tools Nest</span>
                    </h3>
                    <p class="text-gray-400">Your one-stop platform for free online tools that work instantly.</p>
                </div>
                
                <div>
                    <h4 class="font-bold mb-4">Quick Links</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#home" class="hover:text-blue-400 transition">Home</a></li>
                        <li><a href="#tools" class="hover:text-blue-400 transition">All Tools</a></li>
                        <li><a href="#blog" class="hover:text-blue-400 transition">Blog</a></li>
                        <li><a href="#contact" class="hover:text-blue-400 transition">Contact</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="font-bold mb-4">Legal</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" onclick="showLegal('privacy')" class="hover:text-blue-400 transition">Privacy Policy</a></li>
                        <li><a href="#" onclick="showLegal('terms')" class="hover:text-blue-400 transition">Terms of Service</a></li>
                        <li><a href="#" onclick="showLegal('cookies')" class="hover:text-blue-400 transition">Cookie Policy</a></li>
                        <li><a href="#" onclick="showLegal('disclaimer')" class="hover:text-blue-400 transition">Disclaimer</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="font-bold mb-4">Follow Us</h4>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-400 hover:text-blue-400 transition text-2xl"><i class="fab fa-facebook"></i></a>
                        <a href="#" class="text-gray-400 hover:text-blue-400 transition text-2xl"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="text-gray-400 hover:text-blue-400 transition text-2xl"><i class="fab fa-linkedin"></i></a>
                        <a href="#" class="text-gray-400 hover:text-blue-400 transition text-2xl"><i class="fab fa-pinterest"></i></a>
                        <a href="#" class="text-gray-400 hover:text-blue-400 transition text-2xl"><i class="fab fa-instagram"></i></a>
                    </div>
                    <p class="mt-4 text-gray-400 text-sm">Email: support@dailytoolsnest.com</p>
                </div>
            </div>
            <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
                <p>&copy; 2024 Daily Tools Nest. All rights reserved. All tools are free to use.</p>
            </div>
        </div>
    </footer>

    <!-- Legal Pages Modal -->
    <div id="legalModal" class="hidden fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-white rounded-2xl p-6 max-w-2xl w-full max-h-[80vh] overflow-y-auto">
            <div class="flex justify-between items-center mb-4">
                <h3 id="legalTitle" class="text-2xl font-bold"></h3>
                <button onclick="closeLegal()" class="text-gray-500 hover:text-gray-700">&times;</button>
            </div>
            <div id="legalContent" class="prose"></div>
        </div>
    </div>

    <script>
        // Dark Mode Toggle
        const darkModeToggle = document.getElementById('darkModeToggle');
        const body = document.body;
        
        if (localStorage.getItem('darkMode') === 'enabled') {
            body.classList.add('dark-mode');
            darkModeToggle.innerHTML = '<i class="fas fa-sun"></i>';
        }
        
        darkModeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            if (body.classList.contains('dark-mode')) {
                localStorage.setItem('darkMode', 'enabled');
                darkModeToggle.innerHTML = '<i class="fas fa-sun"></i>';
            } else {
                localStorage.setItem('darkMode', 'disabled');
                darkModeToggle.innerHTML = '<i class="fas fa-moon"></i>';
            }
        });
        
        // Mobile Menu Toggle
        document.getElementById('mobileMenuBtn').addEventListener('click', () => {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        });
        
        // Today's usage counter
        let todayUsage = parseInt(localStorage.getItem('todayUsage') || '0');
        const today = new Date().toDateString();
        const lastVisit = localStorage.getItem('lastVisit');
        
        if (lastVisit !== today) {
            todayUsage = 0;
            localStorage.setItem('lastVisit', today);
        }
        document.getElementById('todayUsage').textContent = todayUsage;
        
        function incrementUsage() {
            todayUsage++;
            localStorage.setItem('todayUsage', todayUsage);
            document.getElementById('todayUsage').textContent = todayUsage;
        }
        
        // Tool display functions
        function showTool(toolName) {
            if (toolName === 'qr') {
                document.getElementById('toolsGrid').classList.add('hidden');
                document.getElementById('qrToolInterface').classList.remove('hidden');
                incrementUsage();
                initializeQRGenerator();
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }
        
        function hideTool() {
            document.getElementById('toolsGrid').classList.remove('hidden');
            document.getElementById('qrToolInterface').classList.add('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
        
        let currentComingSoonTool = '';
        let countdownInterval = null;
        
        function showComingSoon(tool, days) {
            currentComingSoonTool = tool;
            const modal = document.getElementById('comingSoonModal');
            const toolNames = {
                unit: 'Unit Converter',
                text: 'Text Case Converter',
                password: 'Password Generator'
            };
            document.getElementById('modalToolName').textContent = toolNames[tool] + ' is under development';
            
            // Start countdown
            if (countdownInterval) clearInterval(countdownInterval);
            updateCountdown(days);
            countdownInterval = setInterval(() => updateCountdown(days), 1000);
            
            modal.classList.remove('hidden');
        }
        
        function updateCountdown(days) {
            const targetDate = new Date();
            targetDate.setDate(targetDate.getDate() + days);
            const now = new Date();
            const diff = targetDate - now;
            
            if (diff <= 0) {
                document.getElementById('countdownDisplay').textContent = 'Launching soon!';
                if (countdownInterval) clearInterval(countdownInterval);
                return;
            }
            
            const daysLeft = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hoursLeft = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutesLeft = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const secondsLeft = Math.floor((diff % (1000 * 60)) / 1000);
            
            document.getElementById('countdownDisplay').innerHTML = `${daysLeft}d ${hoursLeft}h ${minutesLeft}m ${secondsLeft}s`;
        }
        
        function closeModal() {
            document.getElementById('comingSoonModal').classList.add('hidden');
            if (countdownInterval) clearInterval(countdownInterval);
        }
        
        // Notify form submission
        document.getElementById('notifyForm')?.addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('notifyEmail').value;
            if (email) {
                alert(`Thank you! We'll notify you at ${email} when ${currentComingSoonTool} tool launches.`);
                closeModal();
            }
        });
        
        // QR Code Generator Logic
        let currentQRCanvas = null;
        
        function initializeQRGenerator() {
            const qrType = document.getElementById('qrType');
            const dynamicInput = document.getElementById('dynamicInput');
            const generateBtn = document.getElementById('generateBtn');
            
            qrType.addEventListener('change', function() {
                const type = this.value;
                let html = '';
                let placeholder = '';
                let label = '';
                
                switch(type) {
                    case 'url':
                        label = 'Enter URL';
                        placeholder = 'https://example.com';
                        break;
                    case 'text':
                        label = 'Enter Text';
                        placeholder = 'Enter your text here...';
                        break;
                    case 'email':
                        label = 'Email Address';
                        placeholder = 'example@email.com';
                        html += '<input type="email" id="emailSubject" placeholder="Subject (Optional)" class="w-full px-4 py-2 border border-gray-300 rounded-lg mt-2">';
                        break;
                    case 'phone':
                        label = 'Phone Number';
                        placeholder = '+1234567890';
                        break;
                    case 'sms':
                        label = 'Phone Number';
                        placeholder = '+1234567890';
                        html += '<textarea id="smsMessage" placeholder="Message (Optional)" rows="3" class="w-full px-4 py-2 border border-gray-300 rounded-lg mt-2"></textarea>';
                        break;
                    case 'wifi':
                        label = 'WiFi SSID';
                        placeholder = 'WiFi Name';
                        html += '<input type="text" id="wifiPassword" placeholder="Password" class="w-full px-4 py-2 border border-gray-300 rounded-lg mt-2">';
                        html += '<select id="wifiEncryption" class="w-full px-4 py-2 border border-gray-300 rounded-lg mt-2"><option value="WPA">WPA/WPA2</option><option value="WEP">WEP</option><option value="nopass">No Encryption</option></select>';
                        break;
                }
                
                dynamicInput.innerHTML = `<label class="block text-sm font-medium mb-2">${label}</label>
                                          <input type="text" id="qrValue" placeholder="${placeholder}" class="w-full px-4 py-2 border border-gray-300 rounded-lg">${html}`;
            });
            
            function generateQR() {
                const type = qrType.value;
                let value = '';
                const fgColor = document.getElementById('fgColor').value;
                const bgColor = document.getElementById('bgColor').value;
                const size = parseInt(document.getElementById('size').value);
                const errorCorrection = document.getElementById('errorCorrection').value;
                
                const mainInput = document.getElementById('qrValue');
                if (!mainInput || !mainInput.value) {
                    alert('Please enter a value');
                    return;
                }
                
                switch(type) {
                    case 'url':
                    case 'text':
                        value = mainInput.value;
                        break;
                    case 'email':
                        const subject = document.getElementById('emailSubject')?.value;
                        value = subject ? `mailto:${mainInput.value}?subject=${encodeURIComponent(subject)}` : `mailto:${mainInput.value}`;
                        break;
                    case 'phone':
                        value = `tel:${mainInput.value}`;
                        break;
                    case 'sms':
                        const message = document.getElementById('smsMessage')?.value;
                        value = message ? `sms:${mainInput.value}?body=${encodeURIComponent(message)}` : `sms:${mainInput.value}`;
                        break;
                    case 'wifi':
                        const password = document.getElementById('wifiPassword')?.value;
                        const encryption = document.getElementById('wifiEncryption')?.value;
                        value = `WIFI:T:${encryption};S:${mainInput.value};P:${password};;`;
                        break;
                }
                
                if (!value) {
                    alert('Please fill in all required fields');
                    return;
                }
                
                const qrContainer = document.getElementById('qrcode');
                qrContainer.innerHTML = '<div class="loader"></div>';
                
                setTimeout(() => {
                    qrContainer.innerHTML = '';
                    try {
                        new QRCode(qrContainer, {
                            text: value,
                            width: size,
                            height: size,
                            colorDark: fgColor,
                            colorLight: bgColor,
                            correctLevel: QRCode.CorrectLevel[errorCorrection]
                        });
                        
                        setTimeout(() => {
                            const qrImage = qrContainer.querySelector('img');
                            if (qrImage) {
                                currentQRCanvas = qrImage;
                                const logoFile = document.getElementById('logoUpload').files[0];
                                if (logoFile) {
                                    addLogoToQR(qrContainer, logoFile);
                                }
                            }
                            updateEmbedCode(value);
                        }, 100);
                    } catch (error) {
                        qrContainer.innerHTML = '<div class="text-red-500">Error generating QR code. Please try again.</div>';
                    }
                }, 100);
            }
            
            function addLogoToQR(container, logoFile) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const img = container.querySelector('img');
                    if (img) {
                        const canvas = document.createElement('canvas');
                        canvas.width = img.width;
                        canvas.height = img.height;
                        const ctx = canvas.getContext('2d');
                        ctx.drawImage(img, 0, 0, img.width, img.height);
                        
                        const logo = new Image();
                        logo.onload = function() {
                            const logoSize = img.width * 0.2;
                            const x = (img.width - logoSize) / 2;
                            const y = (img.height - logoSize) / 2;
                            ctx.fillStyle = 'white';
                            ctx.fillRect(x - 5, y - 5, logoSize + 10, logoSize + 10);
                            ctx.drawImage(logo, x, y, logoSize, logoSize);
                            img.src = canvas.toDataURL();
                            currentQRCanvas = img;
                        };
                        logo.src = e.target.result;
                    }
                };
                reader.readAsDataURL(logoFile);
            }
            
            function updateEmbedCode(value) {
                const embedCode = `<img src="https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=${encodeURIComponent(value)}" alt="QR Code">`;
                document.getElementById('embedCode').value = embedCode;
            }
            
            generateBtn.addEventListener('click', generateQR);
            
            document.getElementById('downloadPNG').addEventListener('click', () => {
                const qrImage = document.querySelector('#qrcode img');
                if (qrImage) {
                    const link = document.createElement('a');
                    link.download = 'qrcode.png';
                    link.href = qrImage.src;
                    link.click();
                } else {
                    alert('Generate a QR code first');
                }
            });
            
            document.getElementById('downloadSVG').addEventListener('click', () => {
                alert('SVG download coming soon with our premium features. All tools remain free!');
            });
            
            document.getElementById('copyClipboard').addEventListener('click', async () => {
                const qrImage = document.querySelector('#qrcode img');
                if (qrImage) {
                    try {
                        const response = await fetch(qrImage.src);
                        const blob = await response.blob();
                        await navigator.clipboard.write([new ClipboardItem({[blob.type]: blob})]);
                        alert('QR code copied to clipboard!');
                    } catch (err) {
                        alert('Failed to copy. Please try again.');
                    }
                } else {
                    alert('Generate a QR code first');
                }
            });
            
            document.getElementById('printQR').addEventListener('click', () => {
                const qrImage = document.querySelector('#qrcode img');
                if (qrImage) {
                    const printWindow = window.open('', '_blank');
                    printWindow.document.write(`
                        <html>
                            <head><title>Print QR Code</title></head>
                            <body style="display:flex;justify-content:center;align-items:center;height:100vh">
                                <img src="${qrImage.src}" style="max-width:80%">
                            </body>
                        </html>
                    `);
                    printWindow.print();
                }
            });
            
            document.getElementById('copyEmbed').addEventListener('click', () => {
                const embedCode = document.getElementById('embedCode');
                embedCode.select();
                document.execCommand('copy');
                alert('Embed code copied to clipboard!');
            });
            
            // Initialize with default
            setTimeout(() => {
                const defaultInput = document.getElementById('qrValue');
                if (defaultInput) defaultInput.value = 'https://dailytoolsnest.com';
                generateQR();
            }, 100);
        }
        
        // Blog Posts
        const blogPosts = [
            {
                title: "10 Free Online Tools That Boost Productivity in 2024",
                date: "Jan 15, 2024",
                author: "Productivity Team",
                excerpt: "Discover the best free online tools that can help you work smarter, not harder. From QR generators to converters.",
                readTime: "5 min read"
            },
            {
                title: "How to Create Professional QR Codes for Your Business",
                date: "Jan 10, 2024",
                author: "Marketing Team",
                excerpt: "Learn the best practices for creating custom QR codes that maintain your brand identity while ensuring scannability.",
                readTime: "4 min read"
            },
            {
                title: "Coming Soon: Unit Converter – Everything You Need to Know",
                date: "Jan 5, 2024",
                author: "Development Team",
                excerpt: "Preview our upcoming unit converter tool that will support length, weight, temperature, and volume conversions.",
                readTime: "3 min read"
            }
        ];
        
        function loadBlogPosts() {
            const container = document.getElementById('blogPosts');
            container.innerHTML = blogPosts.map(post => `
                <div class="bg-white rounded-xl shadow-md overflow-hidden hover:shadow-xl transition">
                    <div class="h-48 bg-gradient-to-r from-blue-500 to-purple-600 flex items-center justify-center">
                        <i class="fas fa-newspaper fa-4x text-white opacity-50"></i>
                    </div>
                    <div class="p-6">
                        <div class="flex items-center text-sm text-gray-500 mb-2">
                            <span>${post.date}</span>
                            <span class="mx-2">•</span>
                            <span>${post.readTime}</span>
                        </div>
                        <h3 class="text-xl font-bold mb-2">${post.title}</h3>
                        <p class="text-gray-600 mb-3">${post.excerpt}</p>
                        <div class="flex justify-between items-center">
                            <span class="text-sm text-gray-500">By ${post.author}</span>
                            <a href="#" class="text-blue-600 font-semibold hover:text-blue-700">Read More →</a>
                        </div>
                    </div>
                </div>
            `).join('');
        }
        
        loadBlogPosts();
        
        // Contact Form
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const message = document.getElementById('contactMessage');
            message.classList.remove('hidden');
            message.textContent = 'Thank you! We\'ll get back to you soon.';
            setTimeout(() => {
                message.classList.add('hidden');
            }, 3000);
            this.reset();
        });
        
        // Search functionality
        document.getElementById('searchTools').addEventListener('input', function(e) {
            const searchTerm = e.target.value.toLowerCase();
            const toolCards = document.querySelectorAll('.tool-card');
            toolCards.forEach(card => {
                const title = card.querySelector('h3').textContent.toLowerCase();
                const desc = card.querySelector('p').textContent.toLowerCase();
                if (title.includes(searchTerm) || desc.includes(searchTerm)) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        });
        
        // Legal Pages
        function showLegal(page) {
            const modal = document.getElementById('legalModal');
            const title = document.getElementById('legalTitle');
            const content = document.getElementById('legalContent');
            
            const legalContent = {
                privacy: {
                    title: 'Privacy Policy',
                    content: `<p>Last updated: January 2024</p>
                    <h3>1. Information We Collect</h3>
                    <p>Daily Tools Nest does not collect any personal information unless voluntarily provided by users (e.g., email for notifications). All tools work locally in your browser.</p>
                    <h3>2. Cookies</h3>
                    <p>We use cookies only for dark mode preference and usage counters. No tracking cookies are used.</p>
                    <h3>3. Third-Party Services</h3>
                    <p>We display ads from Adsterra. Please review their privacy policy separately.</p>
                    <h3>4. Data Security</h3>
                    <p>Your data never leaves your browser. QR codes are generated locally.</p>`
                },
                terms: {
                    title: 'Terms of Service',
                    content: `<p>Last updated: January 2024</p>
                    <h3>1. Acceptance of Terms</h3>
                    <p>By using Daily Tools Nest, you agree to these terms.</p>
                    <h3>2. Use of Tools</h3>
                    <p>All tools are provided "as is" for personal and commercial use. We reserve the right to modify or discontinue any tool.</p>
                    <h3>3. Prohibited Activities</h3>
                    <p>You may not use our tools for illegal activities or to generate malicious content.</p>
                    <h3>4. Disclaimer</h3>
                    <p>We are not responsible for any damages resulting from tool usage.</p>`
                },
                cookies: {
                    title: 'Cookie Policy',
                    content: `<p>Last updated: January 2024</p>
                    <h3>What Are Cookies</h3>
                    <p>Cookies are small text files stored on your device.</p>
                    <h3>How We Use Cookies</h3>
                    <p>We use localStorage (similar to cookies) for:</p>
                    <ul><li>Dark mode preference</li><li>Daily usage counter</li></ul>
                    <h3>Managing Cookies</h3>
                    <p>You can clear localStorage through your browser settings.</p>`
                },
                disclaimer: {
                    title: 'Disclaimer',
                    content: `<p>Last updated: January 2024</p>
                    <h3>No Warranties</h3>
                    <p>Daily Tools Nest provides tools "as is" without any warranties.</p>
                    <h3>External Links</h3>
                    <p>We may link to third-party websites. We are not responsible for their content.</p>
                    <h3>Accuracy</h3>
                    <p>While we strive for accuracy, tools may occasionally have errors.</p>
                    <h3>Limitation of Liability</h3>
                    <p>Daily Tools Nest is not liable for any indirect or consequential damages.</p>`
                }
            };
            
            const selected = legalContent[page];
            title.textContent = selected.title;
            content.innerHTML = selected.content;
            modal.classList.remove('hidden');
        }
        
        function closeLegal() {
            document.getElementById('legalModal').classList.add('hidden');
        }
        
        // Schema.org markup
        const script = document.createElement('script');
        script.type = 'application/ld+json';
        script.text = JSON.stringify({
            "@context": "https://schema.org",
            "@type": "WebSite",
            "name": "Daily Tools Nest",
            "description": "Free online tools collection including QR code generator, unit converter, text tools, and password generator.",
            "url": "https://dailytoolsnest.com",
            "potentialAction": {
                "@type": "SearchAction",
                "target": "https://dailytoolsnest.com/?s={search_term_string}",
                "query-input": "required name=search_term_string"
            }
        });
        document.head.appendChild(script);
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                const href = this.getAttribute('href');
                if (href === '#') return;
                const target = document.querySelector(href);
                if (target) {
                    e.preventDefault();
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
    </script>
</body>
</html>
