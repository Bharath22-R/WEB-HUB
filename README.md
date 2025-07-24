<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DressHub - Online Dress Shopping</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        .product-card:hover {
            transform: translateY(-4px);
            transition: transform 0.3s ease;
        }
        .filter-sidebar {
            max-height: calc(100vh - 120px);
            overflow-y: auto;
        }
        .orange-gradient {
            background: linear-gradient(135deg, #FF8C42, #FF6B35, #FF4500);
        }
        .black-orange-gradient {
            background: linear-gradient(135deg, #000000, #1a1a1a, #FF8C42);
        }
        .page-transition {
            transition: all 0.3s ease-in-out;
        }
        .hidden {
            display: none;
        }
        .product-image-main {
            transition: transform 0.3s ease;
        }
        .product-image-main:hover {
            transform: scale(1.05);
        }
        .thumbnail-image {
            transition: all 0.3s ease;
        }
        .thumbnail-image:hover {
            transform: scale(1.1);
        }
        .review-stars {
            color: #FF8C42;
        }
    </style>
</head>
<body class="bg-gray-900">
    <!-- Header -->
    <header class="bg-black shadow-lg sticky top-0 z-50 border-b border-orange-400">
        <div class="container mx-auto px-4">
            <!-- Top Bar -->
            <div class="flex items-center justify-between py-2 text-sm border-b border-gray-800">
                <div class="flex space-x-4">
                    <span class="text-orange-300">Free Shipping on orders above ₹999</span>
                </div>
                <div class="flex space-x-4">
                    <a href="#" class="hover:text-orange-400 text-gray-300">Track Order</a>
                    <a href="#" class="hover:text-orange-400 text-gray-300">Help</a>
                </div>
            </div>
            
            <!-- Main Header -->
            <div class="flex items-center justify-between py-4">
                <!-- Logo -->
                <div class="flex items-center">
                    <h1 class="text-2xl font-bold cursor-pointer" onclick="showHomePage()">
                        <span class="text-white">Dress</span><span class="text-orange-400">Hub</span>
                    </h1>
                </div>
                
                <!-- Search Bar -->
                <div class="flex-1 max-w-xl mx-8">
                    <div class="relative">
                        <input type="text" placeholder="Search for dresses, brands, and more..." 
                               class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded-lg focus:outline-none focus:border-orange-400 text-white placeholder-gray-400">
                        <button class="absolute right-3 top-2.5 text-gray-400 hover:text-orange-400">
                            <i class="fas fa-search"></i>
                        </button>
                    </div>
                </div>
                
                <!-- Right Icons -->
                <div class="flex items-center space-x-6">
                    <a href="#" class="flex flex-col items-center text-gray-300 hover:text-orange-400">
                        <i class="fas fa-user text-lg"></i>
                        <span class="text-xs">Profile</span>
                    </a>
                    <a href="#" class="flex flex-col items-center text-gray-300 hover:text-orange-400">
                        <i class="fas fa-heart text-lg"></i>
                        <span class="text-xs">Wishlist</span>
                    </a>
                    <a href="#" class="flex flex-col items-center text-gray-300 hover:text-orange-400 relative">
                        <i class="fas fa-shopping-bag text-lg"></i>
                        <span class="text-xs">Bag</span>
                        <span class="absolute -top-2 -right-2 bg-orange-400 text-black text-xs rounded-full h-5 w-5 flex items-center justify-center font-semibold">3</span>
                    </a>
                </div>
            </div>
            
            <!-- Navigation -->
            <nav class="py-3 border-t border-gray-800">
                <ul class="flex space-x-8">
                    <li><a href="#" class="text-gray-300 hover:text-orange-400 font-medium">Women</a></li>
                    <li><a href="#" class="text-gray-300 hover:text-orange-400 font-medium">Men</a></li>
                    <li><a href="#" class="text-gray-300 hover:text-orange-400 font-medium">Kids</a></li>
                    <li><a href="#" class="text-gray-300 hover:text-orange-400 font-medium">Home & Living</a></li>
                    <li><a href="#" class="text-gray-300 hover:text-orange-400 font-medium">Beauty</a></li>
                    <li><a href="#" class="text-orange-400 font-medium border-b-2 border-orange-400">Dresses</a></li>
                    <li><a href="#" class="text-gray-300 hover:text-orange-400 font-medium">Celebrity Suits</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Home Page -->
    <div id="homePage" class="page-transition">
        <!-- Breadcrumb -->
        <div class="container mx-auto px-4 py-3">
            <nav class="text-sm">
                <a href="#" class="text-gray-400 hover:text-orange-400">Home</a>
                <span class="mx-2 text-gray-500">/</span>
                <a href="#" class="text-gray-400 hover:text-orange-400">Women</a>
                <span class="mx-2 text-gray-500">/</span>
                <span class="text-orange-400">Dresses</span>
            </nav>
        </div>

        <!-- Celebrity Collection Banner -->
        <div class="container mx-auto px-4 mb-6">
            <div class="black-orange-gradient rounded-lg p-6 text-white">
                <div class="flex items-center justify-between">
                    <div>
                        <h2 class="text-2xl font-bold mb-2">✨ Celebrity Suits Collection</h2>
                        <p class="text-orange-200">Wear what your favorite movie heroes wore! Get the iconic looks from blockbuster films.</p>
                    </div>
                    <div class="hidden md:block">
                        <i class="fas fa-star text-4xl text-orange-300"></i>
                    </div>
                </div>
            </div>
        </div>

        <!-- Main Content -->
        <div class="container mx-auto px-4 pb-8">
            <div class="flex gap-6">
                <!-- Sidebar Filters -->
                <aside class="w-64 bg-black rounded-lg shadow-lg p-6 filter-sidebar border border-gray-800">
                    <h3 class="font-semibold text-lg mb-4 text-orange-400">Filters</h3>
                    
                    <!-- Categories -->
                    <div class="mb-6">
                        <h4 class="font-medium mb-3 text-white">Categories</h4>
                        <div class="space-y-2">
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Casual Dresses</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Party Dresses</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Maxi Dresses</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Mini Dresses</span>
                            </label>
                        </div>
                    </div>

                    <!-- Price Range -->
                    <div class="mb-6">
                        <h4 class="font-medium mb-3 text-white">Price</h4>
                        <div class="space-y-2">
                            <label class="flex items-center">
                                <input type="radio" name="price" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Under ₹500</span>
                            </label>
                            <label class="flex items-center">
                                <input type="radio" name="price" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">₹500 - ₹1000</span>
                            </label>
                            <label class="flex items-center">
                                <input type="radio" name="price" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">₹1000 - ₹2000</span>
                            </label>
                            <label class="flex items-center">
                                <input type="radio" name="price" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Above ₹2000</span>
                            </label>
                        </div>
                    </div>

                    <!-- Brand -->
                    <div class="mb-6">
                        <h4 class="font-medium mb-3 text-white">Brand</h4>
                        <div class="space-y-2">
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Zara</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">H&M</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Forever 21</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Vero Moda</span>
                            </label>
                        </div>
                    </div>

                    <!-- Size -->
                    <div class="mb-6">
                        <h4 class="font-medium mb-3 text-white">Size</h4>
                        <div class="grid grid-cols-3 gap-2">
                            <button class="border border-gray-600 py-1 px-2 text-sm hover:border-orange-400 hover:text-orange-400 text-gray-300 bg-gray-800">XS</button>
                            <button class="border border-gray-600 py-1 px-2 text-sm hover:border-orange-400 hover:text-orange-400 text-gray-300 bg-gray-800">S</button>
                            <button class="border border-gray-600 py-1 px-2 text-sm hover:border-orange-400 hover:text-orange-400 text-gray-300 bg-gray-800">M</button>
                            <button class="border border-gray-600 py-1 px-2 text-sm hover:border-orange-400 hover:text-orange-400 text-gray-300 bg-gray-800">L</button>
                            <button class="border border-gray-600 py-1 px-2 text-sm hover:border-orange-400 hover:text-orange-400 text-gray-300 bg-gray-800">XL</button>
                            <button class="border border-gray-600 py-1 px-2 text-sm hover:border-orange-400 hover:text-orange-400 text-gray-300 bg-gray-800">XXL</button>
                        </div>
                    </div>

                    <!-- Color -->
                    <div class="mb-6">
                        <h4 class="font-medium mb-3 text-white">Color</h4>
                        <div class="grid grid-cols-6 gap-2">
                            <div class="w-8 h-8 bg-black rounded-full border-2 border-gray-600 cursor-pointer hover:border-orange-400"></div>
                            <div class="w-8 h-8 bg-white rounded-full border-2 border-gray-600 cursor-pointer hover:border-orange-400"></div>
                            <div class="w-8 h-8 bg-red-500 rounded-full border-2 border-gray-600 cursor-pointer hover:border-orange-400"></div>
                            <div class="w-8 h-8 bg-blue-500 rounded-full border-2 border-gray-600 cursor-pointer hover:border-orange-400"></div>
                            <div class="w-8 h-8 bg-green-500 rounded-full border-2 border-gray-600 cursor-pointer hover:border-orange-400"></div>
                            <div class="w-8 h-8 bg-orange-400 rounded-full border-2 border-gray-600 cursor-pointer hover:border-orange-400"></div>
                        </div>
                    </div>

                    <!-- Celebrity Collection -->
                    <div class="mb-6">
                        <h4 class="font-medium mb-3 text-white">Celebrity Collection</h4>
                        <div class="space-y-2">
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Wonder Woman</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Black Widow</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Captain Marvel</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Hermione Granger</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Katniss Everdeen</span>
                            </label>
                        </div>
                    </div>

                    <!-- Movie Genre -->
                    <div class="mb-6">
                        <h4 class="font-medium mb-3 text-white">Movie Genre</h4>
                        <div class="space-y-2">
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Action/Superhero</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Fantasy</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Romance</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="mr-2 accent-orange-400">
                                <span class="text-sm text-gray-300">Period Drama</span>
                            </label>
                        </div>
                    </div>
                </aside>

                <!-- Product Grid -->
                <main class="flex-1">
                    <!-- Sort and Filter Bar -->
                    <div class="bg-black rounded-lg shadow-lg p-4 mb-6 border border-gray-800">
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-4">
                                <span class="text-gray-300">Showing 1-24 of 1,234 results</span>
                            </div>
                            <div class="flex items-center space-x-4">
                                <span class="text-sm text-gray-300">Sort by:</span>
                                <select class="bg-gray-800 border border-gray-600 rounded px-3 py-1 text-sm focus:outline-none focus:border-orange-400 text-white">
                                    <option>Popularity</option>
                                    <option>Price: Low to High</option>
                                    <option>Price: High to Low</option>
                                    <option>Newest First</option>
                                    <option>Customer Rating</option>
                                </select>
                            </div>
                        </div>
                    </div>

                    <!-- Product Grid -->
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
                        <!-- Celebrity Product Card 1 - Wonder Woman -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Wonder Woman Inspired Dress', 'DC Collection', '₹3,499', '₹4,999', '/images/wonder-woman-dress.jpg', 'Wonder Woman', 'CELEBRITY', 4.8, 324, true)">
                            <div class="relative">
                                <img src="/images/wonder-woman-dress.jpg" alt="Wonder Woman Inspired Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Wonder Woman
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Wonder Woman Inspired Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">DC Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in Wonder Woman (2017)
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(324)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹3,499</span>
                                    <span class="text-sm text-gray-500 line-through">₹4,999</span>
                                </div>
                            </div>
                        </div>

                        <!-- Product Card 2 - Floral Summer Dress -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Floral Summer Dress', 'H&M', '₹899', '', '/images/floral-summer-dress.jpg', '', '', 4.5, 89, false)">
                            <div class="relative">
                                <img src="/images/floral-summer-dress.jpg" alt="Floral Summer Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="fas fa-heart text-orange-400"></i>
                                </button>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Floral Summer Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">H&M</p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(89)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹899</span>
                                </div>
                            </div>
                        </div>

                        <!-- Celebrity Product Card 2 - Black Widow -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Black Widow Tactical Dress', 'Marvel Collection', '₹2,999', '', '/images/black-widow-dress.jpg', 'Black Widow', 'CELEBRITY', 4.7, 267, true)">
                            <div class="relative">
                                <img src="/images/black-widow-dress.jpg" alt="Black Widow Inspired Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Black Widow
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Black Widow Tactical Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">Marvel Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in Avengers series
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(267)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹2,999</span>
                                </div>
                            </div>
                        </div>

                        <!-- Product Card 4 - Blue Maxi Dress -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Blue Maxi Dress', 'Vero Moda', '₹1,249', '₹2,499', '/images/blue-maxi-dress.jpg', '', '', 4.6, 156, false)">
                            <div class="relative">
                                <img src="/images/blue-maxi-dress.jpg" alt="Blue Maxi Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 bg-red-600 text-white px-2 py-1 text-xs rounded">50% OFF</div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Blue Maxi Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">Vero Moda</p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(156)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹1,249</span>
                                    <span class="text-sm text-gray-500 line-through">₹2,499</span>
                                </div>
                            </div>
                        </div>

                        <!-- Celebrity Product Card 3 - Hermione Granger -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Hermione Yule Ball Dress', 'Wizarding Collection', '₹4,299', '₹5,999', '/images/hermione-dress.jpg', 'Harry Potter', 'CELEBRITY', 4.8, 445, true)">
                            <div class="relative">
                                <img src="/images/hermione-dress.jpg" alt="Hermione Inspired Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="fas fa-heart text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Harry Potter
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Hermione Yule Ball Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">Wizarding Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in Goblet of Fire
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(445)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹4,299</span>
                                    <span class="text-sm text-gray-500 line-through">₹5,999</span>
                                </div>
                            </div>
                        </div>

                        <!-- Product Card 6 - Green Midi Dress -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Green Midi Dress', 'H&M', '₹1,124', '₹1,499', '/images/green-midi-dress.jpg', '', '', 4.6, 203, false)">
                            <div class="relative">
                                <img src="/images/green-midi-dress.jpg" alt="Green Midi Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 bg-red-600 text-white px-2 py-1 text-xs rounded">25% OFF</div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Green Midi Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">H&M</p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(203)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹1,124</span>
                                    <span class="text-sm text-gray-500 line-through">₹1,499</span>
                                </div>
                            </div>
                        </div>

                        <!-- Celebrity Product Card 4 - Captain Marvel -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Captain Marvel Power Dress', 'Marvel Collection', '₹3,799', '', '/images/captain-marvel-dress.jpg', 'Captain Marvel', 'CELEBRITY', 4.7, 189, true)">
                            <div class="relative">
                                <img src="/images/captain-marvel-dress.jpg" alt="Captain Marvel Inspired Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Captain Marvel
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Captain Marvel Power Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">Marvel Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in Captain Marvel (2019)
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(189)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹3,799</span>
                                </div>
                            </div>
                        </div>

                        <!-- Celebrity Product Card 5 - Katniss Everdeen -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Katniss Mockingjay Dress', 'Hunger Games Collection', '₹3,299', '₹4,599', '/images/katniss-dress.jpg', 'Hunger Games', 'CELEBRITY', 4.7, 298, true)">
                            <div class="relative">
                                <img src="/images/katniss-dress.jpg" alt="Katniss Mockingjay Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Hunger Games
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Mockingjay Fire Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">Hunger Games Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in Catching Fire
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(298)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹3,299</span>
                                    <span class="text-sm text-gray-500 line-through">₹4,599</span>
                                </div>
                            </div>
                        </div>

                        <!-- Celebrity Product Card 6 - Elsa Frozen -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Elsa Ice Queen Dress', 'Disney Collection', '₹4,599', '', '/images/elsa-dress.jpg', 'Frozen', 'CELEBRITY', 4.9, 567, true)">
                            <div class="relative">
                                <img src="/images/elsa-dress.jpg" alt="Elsa Inspired Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Frozen
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Elsa Ice Queen Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">Disney Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in Frozen
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(567)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹4,599</span>
                                </div>
                            </div>
                        </div>

                        <!-- Celebrity Product Card 7 - Belle Beauty and the Beast -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Belle Golden Ball Gown', 'Disney Collection', '₹5,299', '₹6,999', '/images/belle-dress.jpg', 'Beauty & Beast', 'CELEBRITY', 4.8, 423, true)">
                            <div class="relative">
                                <img src="/images/belle-dress.jpg" alt="Belle Inspired Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="fas fa-heart text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Beauty & Beast
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Belle Golden Ball Gown</h3>
                                <p class="text-sm text-gray-600 mb-2">Disney Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in Beauty and the Beast
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(423)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹5,299</span>
                                    <span class="text-sm text-gray-500 line-through">₹6,999</span>
                                </div>
                            </div>
                        </div>

                        <!-- Celebrity Product Card 8 - Ariel Little Mermaid -->
                        <div class="bg-white rounded-lg shadow-lg overflow-hidden product-card cursor-pointer border border-gray-200 hover:border-orange-400 hover:shadow-xl" onclick="showProductPage('Ariel Mermaid Dress', 'Disney Collection', '₹4,199', '', '/images/ariel-dress.jpg', 'Little Mermaid', 'CELEBRITY', 4.6, 334, true)">
                            <div class="relative">
                                <img src="/images/ariel-dress.jpg" alt="Ariel Inspired Dress" class="w-full h-64 object-cover">
                                <button class="absolute top-3 right-3 bg-white rounded-full p-2 shadow-md hover:bg-gray-50 border border-gray-200" onclick="event.stopPropagation(); toggleWishlist(this)">
                                    <i class="far fa-heart text-gray-600 hover:text-orange-400"></i>
                                </button>
                                <div class="absolute top-3 left-3 orange-gradient text-white px-2 py-1 text-xs rounded font-semibold">CELEBRITY</div>
                                <div class="absolute bottom-3 left-3 bg-black bg-opacity-80 text-orange-400 px-2 py-1 text-xs rounded border border-orange-400">
                                    <i class="fas fa-film mr-1"></i>Little Mermaid
                                </div>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 mb-1">Ariel Mermaid Dress</h3>
                                <p class="text-sm text-gray-600 mb-2">Disney Collection</p>
                                <p class="text-xs text-orange-500 mb-2">
                                    <i class="fas fa-star mr-1"></i>As seen in The Little Mermaid
                                </p>
                                <div class="flex items-center mb-2">
                                    <div class="flex text-orange-400 text-sm">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-xs text-gray-500 ml-1">(334)</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="text-lg font-semibold text-orange-500">₹4,199</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Pagination -->
                    <div class="flex justify-center mt-8">
                        <nav class="flex items-center space-x-2">
                            <button class="px-3 py-2 text-gray-500 hover:text-orange-400 disabled:opacity-50" disabled>
                                <i class="fas fa-chevron-left"></i>
                            </button>
                            <button class="px-3 py-2 bg-orange-400 text-white rounded font-semibold">1</button>
                            <button class="px-3 py-2 text-gray-300 hover:text-orange-400 bg-gray-800 rounded">2</button>
                            <button class="px-3 py-2 text-gray-300 hover:text-orange-400 bg-gray-800 rounded">3</button>
                            <button class="px-3 py-2 text-gray-300 hover:text-orange-400 bg-gray-800 rounded">4</button>
                            <span class="px-3 py-2 text-gray-500">...</span>
                            <button class="px-3 py-2 text-gray-300 hover:text-orange-400 bg-gray-800 rounded">52</button>
                            <button class="px-3 py-2 text-gray-300 hover:text-orange-400">
                                <i class="fas fa-chevron-right"></i>
                            </button>
                        </nav>
                    </div>
                </main>
            </div>
        </div>
    </div>

    <!-- Product Detail Page -->
    <div id="productPage" class="page-transition hidden">
        <!-- Breadcrumb -->
        <div class="container mx-auto px-4 py-3">
            <nav class="text-sm">
                <a href="#" class="text-gray-400 hover:text-orange-400 cursor-pointer" onclick="showHomePage()">Home</a>
                <span class="mx-2 text-gray-500">/</span>
                <a href="#" class="text-gray-400 hover:text-orange-400 cursor-pointer" onclick="showHomePage()">Women</a>
                <span class="mx-2 text-gray-500">/</span>
                <a href="#" class="text-gray-400 hover:text-orange-400 cursor-pointer" onclick="showHomePage()">Dresses</a>
                <span class="mx-2 text-gray-500">/</span>
                <span class="text-orange-400" id="productBreadcrumb">Product Details</span>
            </nav>
        </div>

        <div class="container mx-auto px-4 pb-8">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-12">
                <!-- Product Images -->
                <div class="space-y-4">
                    <!-- Main Image -->
                    <div class="bg-white rounded-lg p-4 shadow-lg">
                        <img id="mainProductImage" src="/placeholder.svg" alt="Product Image" class="w-full h-96 object-cover rounded-lg product-image-main">
                    </div>
                    
                    <!-- Thumbnail Images -->
                    <div class="flex space-x-2 overflow-x-auto">
                        <img src="/images/wonder-woman-dress.jpg" alt="Thumbnail 1" class="w-20 h-20 object-cover rounded-lg cursor-pointer thumbnail-image border-2 border-transparent hover:border-orange-400" onclick="changeMainImage(this.src)">
                        <img src="/images/wonder-woman-dress.jpg" alt="Thumbnail 2" class="w-20 h-20 object-cover rounded-lg cursor-pointer thumbnail-image border-2 border-transparent hover:border-orange-400" onclick="changeMainImage(this.src)">
                        <img src="/images/wonder-woman-dress.jpg" alt="Thumbnail 3" class="w-20 h-20 object-cover rounded-lg cursor-pointer thumbnail-image border-2 border-transparent hover:border-orange-400" onclick="changeMainImage(this.src)">
                        <img src="/images/wonder-woman-dress.jpg" alt="Thumbnail 4" class="w-20 h-20 object-cover rounded-lg cursor-pointer thumbnail-image border-2 border-transparent hover:border-orange-400" onclick="changeMainImage(this.src)">
                    </div>
                </div>

                <!-- Product Details -->
                <div class="bg-white rounded-lg p-6 shadow-lg">
                    <div id="celebrityBadge" class="inline-block orange-gradient text-white px-3 py-1 text-sm rounded font-semibold mb-4 hidden">
                        <i class="fas fa-star mr-1"></i>CELEBRITY COLLECTION
                    </div>
                    
                    <h1 id="productTitle" class="text-3xl font-bold text-gray-800 mb-2">Product Title</h1>
                    <p id="productBrand" class="text-lg text-gray-600 mb-4">Brand Name</p>
                    
                    <div id="movieInfo" class="bg-orange-50 border border-orange-200 rounded-lg p-3 mb-4 hidden">
                        <p class="text-orange-700 text-sm">
                            <i class="fas fa-film mr-2"></i>
                            <span id="movieText">As seen in movie</span>
                        </p>
                    </div>

                    <!-- Rating -->
                    <div class="flex items-center mb-4">
                        <div id="productStars" class="flex text-orange-400 text-lg mr-2">
                            <!-- Stars will be populated by JavaScript -->
                        </div>
                        <span id="productRating" class="text-lg font-semibold text-gray-700 mr-2">4.8</span>
                        <span id="productReviewCount" class="text-gray-500">(<span>324</span> reviews)</span>
                    </div>

                    <!-- Price -->
                    <div class="flex items-center space-x-3 mb-6">
                        <span id="productPrice" class="text-3xl font-bold text-orange-500">₹3,499</span>
                        <span id="productOriginalPrice" class="text-xl text-gray-500 line-through hidden">₹4,999</span>
                        <span id="productDiscount" class="bg-green-100 text-green-800 px-2 py-1 rounded text-sm font-semibold hidden">30% OFF</span>
                    </div>

                    <!-- Size Selection -->
                    <div class="mb-6">
                        <h3 class="font-semibold text-gray-800 mb-3">Size</h3>
                        <div class="flex space-x-2">
                            <button class="border-2 border-gray-300 px-4 py-2 rounded hover:border-orange-400 hover:text-orange-400 transition-colors size-btn" onclick="selectSize(this)">XS</button>
                            <button class="border-2 border-gray-300 px-4 py-2 rounded hover:border-orange-400 hover:text-orange-400 transition-colors size-btn" onclick="selectSize(this)">S</button>
                            <button class="border-2 border-gray-300 px-4 py-2 rounded hover:border-orange-400 hover:text-orange-400 transition-colors size-btn" onclick="selectSize(this)">M</button>
                            <button class="border-2 border-gray-300 px-4 py-2 rounded hover:border-orange-400 hover:text-orange-400 transition-colors size-btn" onclick="selectSize(this)">L</button>
                            <button class="border-2 border-gray-300 px-4 py-2 rounded hover:border-orange-400 hover:text-orange-400 transition-colors size-btn" onclick="selectSize(this)">XL</button>
                        </div>
                    </div>

                    <!-- Quantity -->
                    <div class="mb-6">
                        <h3 class="font-semibold text-gray-800 mb-3">Quantity</h3>
                        <div class="flex items-center space-x-3">
                            <button class="border border-gray-300 px-3 py-1 rounded hover:bg-gray-100" onclick="changeQuantity(-1)">-</button>
                            <span id="quantity" class="px-4 py-1 border border-gray-300 rounded">1</span>
                            <button class="border border-gray-300 px-3 py-1 rounded hover:bg-gray-100" onclick="changeQuantity(1)">+</button>
                        </div>
                    </div>

                    <!-- Action Buttons -->
                    <div class="space-y-3">
                        <button class="w-full bg-orange-400 text-white py-3 rounded-lg font-semibold hover:bg-orange-500 transition-colors">
                            <i class="fas fa-shopping-cart mr-2"></i>Add to Cart
                        </button>
                        <button class="w-full bg-orange-600 text-white py-3 rounded-lg font-semibold hover:bg-orange-700 transition-colors">
                            <i class="fas fa-bolt mr-2"></i>Buy Now
                        </button>
                        <button class="w-full border-2 border-orange-400 text-orange-400 py-3 rounded-lg font-semibold hover:bg-orange-50 transition-colors">
                            <i class="fas fa-heart mr-2"></i>Add to Wishlist
                        </button>
                    </div>

                    <!-- Product Features -->
                    <div class="mt-6 pt-6 border-t border-gray-200">
                        <h3 class="font-semibold text-gray-800 mb-3">Product Features</h3>
                        <ul class="space-y-2 text-gray-600">
                            <li class="flex items-center"><i class="fas fa-check text-green-500 mr-2"></i>Premium quality fabric</li>
                            <li class="flex items-center"><i class="fas fa-check text-green-500 mr-2"></i>Machine washable</li>
                            <li class="flex items-center"><i class="fas fa-check text-green-500 mr-2"></i>Perfect fit guarantee</li>
                            <li class="flex items-center"><i class="fas fa-check text-green-500 mr-2"></i>Free shipping & returns</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- Product Tabs -->
            <div class="bg-white rounded-lg shadow-lg mb-8">
                <div class="border-b border-gray-200">
                    <nav class="flex space-x-8 px-6">
                        <button class="py-4 px-2 border-b-2 border-orange-400 text-orange-400 font-semibold tab-btn active" onclick="showTab('description')">Description</button>
                        <button class="py-4 px-2 border-b-2 border-transparent text-gray-500 hover:text-orange-400 font-semibold tab-btn" onclick="showTab('reviews')">Reviews</button>
                        <button class="py-4 px-2 border-b-2 border-transparent text-gray-500 hover:text-orange-400 font-semibold tab-btn" onclick="showTab('shipping')">Shipping & Returns</button>
                    </nav>
                </div>

                <!-- Tab Content -->
                <div class="p-6">
                    <!-- Description Tab -->
                    <div id="descriptionTab" class="tab-content">
                        <h3 class="text-xl font-semibold mb-4">Product Description</h3>
                        <p class="text-gray-600 mb-4">
                            This stunning dress is inspired by the iconic Wonder Woman costume from the 2017 blockbuster movie. 
                            Crafted with premium materials and attention to detail, this dress captures the essence of the 
                            Amazonian warrior princess while maintaining elegance and comfort for everyday wear.
                        </p>
                        <p class="text-gray-600 mb-4">
                            Features include a fitted bodice with gold accents, flowing skirt, and comfortable stretch fabric 
                            that moves with you. Perfect for costume parties, themed events, or when you want to feel like 
                            a superhero in your daily life.
                        </p>
                        <h4 class="font-semibold mb-2">Material & Care:</h4>
                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                            <li>95% Polyester, 5% Spandex</li>
                            <li>Machine wash cold with like colors</li>
                            <li>Tumble dry low heat</li>
                            <li>Do not bleach or iron directly on prints</li>
                        </ul>
                    </div>

                    <!-- Reviews Tab -->
                    <div id="reviewsTab" class="tab-content hidden">
                        <div class="flex items-center justify-between mb-6">
                            <h3 class="text-xl font-semibold">Customer Reviews</h3>
                            <button class="bg-orange-400 text-white px-4 py-2 rounded-lg hover:bg-orange-500">Write a Review</button>
                        </div>

                        <!-- Review Summary -->
                        <div class="bg-gray-50 rounded-lg p-4 mb-6">
                            <div class="flex items-center space-x-4">
                                <div class="text-center">
                                    <div class="text-3xl font-bold text-orange-500" id="avgRating">4.8</div>
                                    <div class="flex text-orange-400 justify-center mb-1">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <div class="text-sm text-gray-600" id="totalReviews">324 reviews</div>
                                </div>
                                <div class="flex-1">
                                    <div class="space-y-1">
                                        <div class="flex items-center">
                                            <span class="text-sm w-8">5★</span>
                                            <div class="flex-1 bg-gray-200 rounded-full h-2 mx-2">
                                                <div class="bg-orange-400 h-2 rounded-full" style="width: 75%"></div>
                                            </div>
                                            <span class="text-sm text-gray-600">243</span>
                                        </div>
                                        <div class="flex items-center">
                                            <span class="text-sm w-8">4★</span>
                                            <div class="flex-1 bg-gray-200 rounded-full h-2 mx-2">
                                                <div class="bg-orange-400 h-2 rounded-full" style="width: 15%"></div>
                                            </div>
                                            <span class="text-sm text-gray-600">49</span>
                                        </div>
                                        <div class="flex items-center">
                                            <span class="text-sm w-8">3★</span>
                                            <div class="flex-1 bg-gray-200 rounded-full h-2 mx-2">
                                                <div class="bg-orange-400 h-2 rounded-full" style="width: 7%"></div>
                                            </div>
                                            <span class="text-sm text-gray-600">23</span>
                                        </div>
                                        <div class="flex items-center">
                                            <span class="text-sm w-8">2★</span>
                                            <div class="flex-1 bg-gray-200 rounded-full h-2 mx-2">
                                                <div class="bg-orange-400 h-2 rounded-full" style="width: 2%"></div>
                                            </div>
                                            <span class="text-sm text-gray-600">6</span>
                                        </div>
                                        <div class="flex items-center">
                                            <span class="text-sm w-8">1★</span>
                                            <div class="flex-1 bg-gray-200 rounded-full h-2 mx-2">
                                                <div class="bg-orange-400 h-2 rounded-full" style="width: 1%"></div>
                                            </div>
                                            <span class="text-sm text-gray-600">3</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Individual Reviews -->
                        <div class="space-y-6">
                            <!-- Review 1 -->
                            <div class="border-b border-gray-200 pb-6">
                                <div class="flex items-start space-x-4">
                                    <div class="w-10 h-10 bg-orange-400 rounded-full flex items-center justify-center text-white font-semibold">S</div>
                                    <div class="flex-1">
                                        <div class="flex items-center space-x-2 mb-2">
                                            <h4 class="font-semibold">Sarah M.</h4>
                                            <div class="flex text-orange-400 text-sm">
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                            </div>
                                            <span class="text-sm text-gray-500">2 days ago</span>
                                        </div>
                                        <p class="text-gray-600 mb-2">
                                            "Absolutely love this dress! The quality is amazing and it fits perfectly. 
                                            I wore it to a costume party and got so many compliments. Definitely feels 
                                            like Wonder Woman!"
                                        </p>
                                        <div class="flex items-center space-x-4 text-sm text-gray-500">
                                            <button class="hover:text-orange-400">👍 Helpful (12)</button>
                                            <button class="hover:text-orange-400">Reply</button>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <!-- Review 2 -->
                            <div class="border-b border-gray-200 pb-6">
                                <div class="flex items-start space-x-4">
                                    <div class="w-10 h-10 bg-orange-400 rounded-full flex items-center justify-center text-white font-semibold">A</div>
                                    <div class="flex-1">
                                        <div class="flex items-center space-x-2 mb-2">
                                            <h4 class="font-semibold">Amanda K.</h4>
                                            <div class="flex text-orange-400 text-sm">
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                            </div>
                                            <span class="text-sm text-gray-500">1 week ago</span>
                                        </div>
                                        <p class="text-gray-600 mb-2">
                                            "Great dress! The material is comfortable and the design is spot-on. 
                                            Shipping was fast too. Would definitely recommend to other Wonder Woman fans!"
                                        </p>
                                        <div class="flex items-center space-x-4 text-sm text-gray-500">
                                            <button class="hover:text-orange-400">👍 Helpful (8)</button>
                                            <button class="hover:text-orange-400">Reply</button>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <!-- Review 3 -->
                            <div class="border-b border-gray-200 pb-6">
                                <div class="flex items-start space-x-4">
                                    <div class="w-10 h-10 bg-orange-400 rounded-full flex items-center justify-center text-white font-semibold">M</div>
                                    <div class="flex-1">
                                        <div class="flex items-center space-x-2 mb-2">
                                            <h4 class="font-semibold">Maria L.</h4>
                                            <div class="flex text-orange-400 text-sm">
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="fas fa-star"></i>
                                                <i class="far fa-star"></i>
                                            </div>
                                            <span class="text-sm text-gray-500">2 weeks ago</span>
                                        </div>
                                        <p class="text-gray-600 mb-2">
                                            "Beautiful dress, but runs a bit small. I ordered my usual size M but should have 
                                            gone with L. The quality is excellent though, and customer service was helpful 
                                            with the exchange."
                                        </p>
                                        <div class="flex items-center space-x-4 text-sm text-gray-500">
                                            <button class="hover:text-orange-400">👍 Helpful (15)</button>
                                            <button class="hover:text-orange-400">Reply</button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Load More Reviews -->
                        <div class="text-center mt-6">
                            <button class="border border-orange-400 text-orange-400 px-6 py-2 rounded-lg hover:bg-orange-50">
                                Load More Reviews
                            </button>
                        </div>
                    </div>

                    <!-- Shipping Tab -->
                    <div id="shippingTab" class="tab-content hidden">
                        <h3 class="text-xl font-semibold mb-4">Shipping & Returns</h3>
                        
                        <div class="grid md:grid-cols-2 gap-6">
                            <div>
                                <h4 class="font-semibold mb-3 text-orange-500">Shipping Information</h4>
                                <ul class="space-y-2 text-gray-600">
                                    <li class="flex items-center"><i class="fas fa-truck text-orange-400 mr-2"></i>Free shipping on orders over ₹999</li>
                                    <li class="flex items-center"><i class="fas fa-clock text-orange-400 mr-2"></i>Standard delivery: 3-5 business days</li>
                                    <li class="flex items-center"><i class="fas fa-bolt text-orange-400 mr-2"></i>Express delivery: 1-2 business days (₹199)</li>
                                    <li class="flex items-center"><i class="fas fa-map-marker-alt text-orange-400 mr-2"></i>Available across India</li>
                                </ul>
                            </div>
                            
                            <div>
                                <h4 class="font-semibold mb-3 text-orange-500">Return Policy</h4>
                                <ul class="space-y-2 text-gray-600">
                                    <li class="flex items-center"><i class="fas fa-undo text-orange-400 mr-2"></i>30-day return policy</li>
                                    <li class="flex items-center"><i class="fas fa-exchange-alt text-orange-400 mr-2"></i>Free exchanges for wrong size</li>
                                    <li class="flex items-center"><i class="fas fa-shield-alt text-orange-400 mr-2"></i>100% authentic guarantee</li>
                                    <li class="flex items-center"><i class="fas fa-headset text-orange-400 mr-2"></i>24/7 customer support</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Similar Products -->
            <div class="bg-white rounded-lg shadow-lg p-6">
                <h3 class="text-2xl font-semibold mb-6 text-gray-800">Similar Products</h3>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <!-- Similar Product 1 -->
                    <div class="border border-gray-200 rounded-lg overflow-hidden hover:shadow-lg transition-shadow cursor-pointer" onclick="showProductPage('Captain Marvel Power Dress', 'Marvel Collection', '₹3,799', '', '/images/captain-marvel-dress.jpg', 'Captain Marvel', 'CELEBRITY', 4.7, 189, true)">
                        <img src="/images/captain-marvel-dress.jpg" alt="Captain Marvel Dress" class="w-full h-48 object-cover">
                        <div class="p-4">
                            <h4 class="font-medium text-gray-800 mb-1">Captain Marvel Power Dress</h4>
                            <p class="text-sm text-gray-600 mb-2">Marvel Collection</p>
                            <div class="flex items-center mb-2">
                                <div class="flex text-orange-400 text-sm">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="text-xs text-gray-500 ml-1">(189)</span>
                            </div>
                            <div class="text-lg font-semibold text-orange-500">₹3,799</div>
                        </div>
                    </div>

                    <!-- Similar Product 2 -->
                    <div class="border border-gray-200 rounded-lg overflow-hidden hover:shadow-lg transition-shadow cursor-pointer" onclick="showProductPage('Black Widow Tactical Dress', 'Marvel Collection', '₹2,999', '', '/images/black-widow-dress.jpg', 'Black Widow', 'CELEBRITY', 4.7, 267, true)">
                        <img src="/images/black-widow-dress.jpg" alt="Black Widow Dress" class="w-full h-48 object-cover">
                        <div class="p-4">
                            <h4 class="font-medium text-gray-800 mb-1">Black Widow Tactical Dress</h4>
                            <p class="text-sm text-gray-600 mb-2">Marvel Collection</p>
                            <div class="flex items-center mb-2">
                                <div class="flex text-orange-400 text-sm">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="text-xs text-gray-500 ml-1">(267)</span>
                            </div>
                            <div class="text-lg font-semibold text-orange-500">₹2,999</div>
                        </div>
                    </div>

                    <!-- Similar Product 3 -->
                    <div class="border border-gray-200 rounded-lg overflow-hidden hover:shadow-lg transition-shadow cursor-pointer" onclick="showProductPage('Hermione Yule Ball Dress', 'Wizarding Collection', '₹4,299', '₹5,999', '/images/hermione-dress.jpg', 'Harry Potter', 'CELEBRITY', 4.8, 445, true)">
                        <img src="/images/hermione-dress.jpg" alt="Hermione Dress" class="w-full h-48 object-cover">
                        <div class="p-4">
                            <h4 class="font-medium text-gray-800 mb-1">Hermione Yule Ball Dress</h4>
                            <p class="text-sm text-gray-600 mb-2">Wizarding Collection</p>
                            <div class="flex items-center mb-2">
                                <div class="flex text-orange-400 text-sm">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="text-xs text-gray-500 ml-1">(445)</span>
                            </div>
                            <div class="flex items-center space-x-2">
                                <span class="text-lg font-semibold text-orange-500">₹4,299</span>
                                <span class="text-sm text-gray-500 line-through">₹5,999</span>
                            </div>
                        </div>
                    </div>

                    <!-- Similar Product 4 -->
                    <div class="border border-gray-200 rounded-lg overflow-hidden hover:shadow-lg transition-shadow cursor-pointer" onclick="showProductPage('Elsa Ice Queen Dress', 'Disney Collection', '₹4,599', '', '/images/elsa-dress.jpg', 'Frozen', 'CELEBRITY', 4.9, 567, true)">
                        <img src="/images/elsa-dress.jpg" alt="Elsa Dress" class="w-full h-48 object-cover">
                        <div class="p-4">
                            <h4 class="font-medium text-gray-800 mb-1">Elsa Ice Queen Dress</h4>
                            <p class="text-sm text-gray-600 mb-2">Disney Collection</p>
                            <div class="flex items-center mb-2">
                                <div class="flex text-orange-400 text-sm">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="text-xs text-gray-500 ml-1">(567)</span>
                            </div>
                            <div class="text-lg font-semibold text-orange-500">₹4,599</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-black text-white mt-12 border-t border-orange-400">
        <div class="container mx-auto px-4 py-12">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Company Info -->
                <div>
                    <h3 class="text-xl font-bold mb-4">
                        <span class="text-white">Dress</span><span class="text-orange-400">Hub</span>
                    </h3>
                    <p class="text-gray-400 mb-4">Your one-stop destination for trendy and affordable dresses.</p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-400 hover:text-orange-400"><i class="fab fa-facebook"></i></a>
                        <a href="#" class="text-gray-400 hover:text-orange-400"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="text-gray-400 hover:text-orange-400"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="text-gray-400 hover:text-orange-400"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>

                <!-- Celebrity & Quick Links -->
                <div>
                    <h4 class="font-semibold mb-4 text-orange-400">Celebrity Collections</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" class="hover:text-orange-400">Marvel Heroes</a></li>
                        <li><a href="#" class="hover:text-orange-400">DC Universe</a></li>
                        <li><a href="#" class="hover:text-orange-400">Disney Princesses</a></li>
                        <li><a href="#" class="hover:text-orange-400">Harry Potter</a></li>
                        <li><a href="#" class="hover:text-orange-400">Hunger Games</a></li>
                    </ul>
                </div>

                <!-- Customer Service -->
                <div>
                    <h4 class="font-semibold mb-4 text-orange-400">Customer Service</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" class="hover:text-orange-400">Contact Us</a></li>
                        <li><a href="#" class="hover:text-orange-400">Track Your Order</a></li>
                        <li><a href="#" class="hover:text-orange-400">Size Guide</a></li>
                        <li><a href="#" class="hover:text-orange-400">Return Policy</a></li>
                        <li><a href="#" class="hover:text-orange-400">FAQ</a></li>
                    </ul>
                </div>

                <!-- Newsletter -->
                <div>
                    <h4 class="font-semibold mb-4 text-orange-400">Stay Updated</h4>
                    <p class="text-gray-400 mb-4">Subscribe to get special offers and updates.</p>
                    <div class="flex">
                        <input type="email" placeholder="Enter your email" 
                               class="flex-1 px-3 py-2 bg-gray-800 border border-gray-700 rounded-l focus:outline-none focus:border-orange-400 text-white placeholder-gray-500">
                        <button class="bg-orange-400 px-4 py-2 rounded-r hover:bg-orange-500 text-white font-semibold">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
            </div>

            <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
                <p>&copy; 2024 <span class="text-white">Dress</span><span class="text-orange-400">Hub</span>. All rights reserved. | <a href="#" class="hover:text-orange-400">Privacy Policy</a> | <a href="#" class="hover:text-orange-400">Terms of Service</a></p>
            </div>
        </div>
    </footer>

    <script>
        let currentQuantity = 1;

        // Page Navigation Functions
        function showHomePage() {
            document.getElementById('homePage').classList.remove('hidden');
            document.getElementById('productPage').classList.add('hidden');
        }

        function showProductPage(title, brand, price, originalPrice, image, movie, badge, rating, reviewCount, isCelebrity) {
            // Hide home page and show product page
            document.getElementById('homePage').classList.add('hidden');
            document.getElementById('productPage').classList.remove('hidden');

            // Update product details
            document.getElementById('productTitle').textContent = title;
            document.getElementById('productBrand').textContent = brand;
            document.getElementById('productPrice').textContent = price;
            document.getElementById('mainProductImage').src = image;
            document.getElementById('productBreadcrumb').textContent = title;

            // Handle original price and discount
            const originalPriceElement = document.getElementById('productOriginalPrice');
            const discountElement = document.getElementById('productDiscount');
            
            if (originalPrice) {
                originalPriceElement.textContent = originalPrice;
                originalPriceElement.classList.remove('hidden');
                
                // Calculate discount percentage
                const currentPrice = parseInt(price.replace('₹', '').replace(',', ''));
                const origPrice = parseInt(originalPrice.replace('₹', '').replace(',', ''));
                const discountPercent = Math.round(((origPrice - currentPrice) / origPrice) * 100);
                
                discountElement.textContent = `${discountPercent}% OFF`;
                discountElement.classList.remove('hidden');
            } else {
                originalPriceElement.classList.add('hidden');
                discountElement.classList.add('hidden');
            }

            // Handle celebrity badge and movie info
            const celebrityBadge = document.getElementById('celebrityBadge');
            const movieInfo = document.getElementById('movieInfo');
            const movieText = document.getElementById('movieText');

            if (isCelebrity && movie) {
                celebrityBadge.classList.remove('hidden');
                movieInfo.classList.remove('hidden');
                movieText.textContent = `As seen in ${movie}`;
            } else {
                celebrityBadge.classList.add('hidden');
                movieInfo.classList.add('hidden');
            }

            // Update rating
            updateRating(rating, reviewCount);

            // Reset quantity and size selection
            currentQuantity = 1;
            document.getElementById('quantity').textContent = currentQuantity;
            
            // Reset size buttons
            const sizeButtons = document.querySelectorAll('.size-btn');
            sizeButtons.forEach(btn => {
                btn.classList.remove('border-orange-400', 'text-orange-400', 'bg-orange-50');
                btn.classList.add('border-gray-300');
            });

            // Scroll to top
            window.scrollTo(0, 0);
        }

        function updateRating(rating, reviewCount) {
            const starsContainer = document.getElementById('productStars');
            const ratingElement = document.getElementById('productRating');
            const reviewCountElement = document.getElementById('productReviewCount');
            const avgRatingElement = document.getElementById('avgRating');
            const totalReviewsElement = document.getElementById('totalReviews');

            // Update rating display
            ratingElement.textContent = rating;
            reviewCountElement.innerHTML = `(<span>${reviewCount}</span> reviews)`;
            
            if (avgRatingElement) avgRatingElement.textContent = rating;
            if (totalReviewsElement) totalReviewsElement.textContent = `${reviewCount} reviews`;

            // Generate stars
            const fullStars = Math.floor(rating);
            const hasHalfStar = rating % 1 !== 0;
            let starsHTML = '';

            for (let i = 0; i < fullStars; i++) {
                starsHTML += '<i class="fas fa-star"></i>';
            }

            if (hasHalfStar) {
                starsHTML += '<i class="fas fa-star-half-alt"></i>';
            }

            const emptyStars = 5 - Math.ceil(rating);
            for (let i = 0; i < emptyStars; i++) {
                starsHTML += '<i class="far fa-star"></i>';
            }

            starsContainer.innerHTML = starsHTML;
        }

        // Product interaction functions
        function changeMainImage(src) {
            document.getElementById('mainProductImage').src = src;
            
            // Update thumbnail borders
            const thumbnails = document.querySelectorAll('.thumbnail-image');
            thumbnails.forEach(thumb => {
                if (thumb.src === src) {
                    thumb.classList.add('border-orange-400');
                    thumb.classList.remove('border-transparent');
                } else {
                    thumb.classList.remove('border-orange-400');
                    thumb.classList.add('border-transparent');
                }
            });
        }

        function selectSize(button) {
            // Remove active class from all size buttons
            const sizeButtons = document.querySelectorAll('.size-btn');
            sizeButtons.forEach(btn => {
                btn.classList.remove('border-orange-400', 'text-orange-400', 'bg-orange-50');
                btn.classList.add('border-gray-300');
            });
            
            // Add active class to clicked button
            button.classList.remove('border-gray-300');
            button.classList.add('border-orange-400', 'text-orange-400', 'bg-orange-50');
        }

        function changeQuantity(change) {
            currentQuantity += change;
            if (currentQuantity < 1) currentQuantity = 1;
            if (currentQuantity > 10) currentQuantity = 10;
            
            document.getElementById('quantity').textContent = currentQuantity;
        }

        // Tab functionality
        function showTab(tabName) {
            // Hide all tab contents
            const tabContents = document.querySelectorAll('.tab-content');
            tabContents.forEach(content => content.classList.add('hidden'));
            
            // Remove active class from all tab buttons
            const tabButtons = document.querySelectorAll('.tab-btn');
            tabButtons.forEach(btn => {
                btn.classList.remove('border-orange-400', 'text-orange-400');
                btn.classList.add('border-transparent', 'text-gray-500');
            });
            
            // Show selected tab content
            document.getElementById(tabName + 'Tab').classList.remove('hidden');
            
            // Add active class to clicked tab button
            event.target.classList.remove('border-transparent', 'text-gray-500');
            event.target.classList.add('border-orange-400', 'text-orange-400');
        }

        // Wishlist functionality
        function toggleWishlist(button) {
            const icon = button.querySelector('i');
            icon.classList.toggle('fas');
            icon.classList.toggle('far');
            icon.classList.toggle('text-orange-400');
            icon.classList.toggle('text-gray-600');
        }

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            // Set first thumbnail as active
            const firstThumbnail = document.querySelector('.thumbnail-image');
            if (firstThumbnail) {
                firstThumbnail.classList.add('border-orange-400');
                firstThumbnail.classList.remove('border-transparent');
            }

            // Add click handlers for filter functionality
            const filterInputs = document.querySelectorAll('input[type="checkbox"], input[type="radio"]');
            filterInputs.forEach(input => {
                input.addEventListener('change', function() {
                    console.log('Filter applied:', this.value);
                });
            });

            // Add click handlers for color selection
            const colorButtons = document.querySelectorAll('aside .rounded-full');
            colorButtons.forEach(button => {
                button.addEventListener('click', function() {
                    // Remove active class from all color buttons
                    colorButtons.forEach(btn => {
                        btn.classList.remove('ring-2', 'ring-orange-400');
                        btn.classList.add('border-gray-600');
                    });
                    
                    // Add active class to clicked button
                    this.classList.remove('border-gray-600');
                    this.classList.add('ring-2', 'ring-orange-400');
                });
            });

            // Add click handlers for size buttons in sidebar
            const sidebarSizeButtons = document.querySelectorAll('aside button');
            sidebarSizeButtons.forEach(button => {
                button.addEventListener('click', function() {
                    // Remove active class from all size buttons
                    sidebarSizeButtons.forEach(btn => {
                        btn.classList.remove('border-orange-400', 'text-orange-400', 'bg-orange-400', 'text-white');
                        btn.classList.add('border-gray-600', 'text-gray-300', 'bg-gray-800');
                    });
                    
                    // Add active class to clicked button
                    this.classList.remove('border-gray-600', 'text-gray-300', 'bg-gray-800');
                    this.classList.add('border-orange-400', 'text-white', 'bg-orange-400');
                });
            });
        });
    </script>
</body>
</html>
