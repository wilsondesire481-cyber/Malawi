<!DOCTYPE html>  <html lang="ny">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Wilson Desire Hub - Malawi Full</title>    <!-- PWA -->    <meta name="theme-color" content="#0f172a">  
  <meta name="mobile-web-app-capable" content="yes">  
  <meta name="apple-mobile-web-app-capable" content="yes">  
  <link rel="manifest" href="data:application/manifest+json,{  
    &quot;name&quot;: &quot;Wilson Desire Hub&quot;,  
    &quot;short_name&quot;: &quot;WilsonHub&quot;,  
    &quot;start_url&quot;: &quot;.&quot;,  
    &quot;display&quot;: &quot;standalone&quot;,  
    &quot;background_color&quot;: &quot;#0f172a&quot;,  
    &quot;theme_color&quot;: &quot;#FFC107&quot;,  
    &quot;description&quot;: &quot;Everything you need, all in one place&quot;,  
    &quot;icons&quot;: [{  
      &quot;src&quot;: &quot;data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNTEyIiBoZWlnaHQ9IjUxMiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iNTEyIiBoZWlnaHQ9IjUxMiIgZmlsbD0iI0ZGQzEwNyIvPjx0ZXh0IHg9IjUwJSIgeT0iNTAlIiBkb21pbmFudC1iYXNlbGluZT0ibWlkZGxlIiB0ZXh0LWFuY2hvcj0ibWlkZGxlIiBmb250LXNpemU9IjgwIiBmb250LXdlaWdodD0iYm9sZCIgZmlsbD0iIzBmMTcyYSI+V0Q8L3RleHQ+PC9zdmc+&quot;,  
      &quot;sizes&quot;: &quot;512x512&quot;,  
      &quot;type&quot;: &quot;image/svg+xml&quot;  
    }]  
  }">    <script src="https://cdn.tailwindcss.com"></script>    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">    <style>  
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');  
    body { font-family: 'Poppins', sans-serif; background: #0f172a; color: white; }  
    .app-screen { display: none; min-height: 100vh; }  
    .app-screen.active { display: block; }  
    .yellow-btn { background: #FFC107; color: #000; font-weight: 600; }  
    .yellow-btn:hover { background: #FFB300; }  
    .nav-active { color: #FFC107; }  
    .card-dark { background-color: #1e293b; }  
    .modal { display: none; }  
    .modal.active { display: flex; }  
  </style>  </head>  
<body class="bg-gray-900">    <!-- SCREEN 1: WELCOME -->    <div id="welcome" class="app-screen active p-6 h-screen flex flex-col justify-center text-center">  
    <h1 class="text-2xl font-bold text-yellow-400 mt-4">WILSON DESIRE HUB</h1>  
    <p class="text-sm text-yellow-400">MALAWI FULL</p>  
    <p class="text-gray-300 mb-12 mt-4">Everything you need,<br>all in one place!</p>  
    <div class="w-full space-y-3">  
      <button onclick="showScreen('login')" class="yellow-btn w-full py-3 rounded-lg">Login</button>  
      <button onclick="showScreen('register')" class="border border-yellow-400 text-yellow-400 w-full py-3 rounded-lg">Create Account</button>  
    </div>  
  </div>    <!-- SCREEN 2: REGISTER -->    <div id="register" class="app-screen p-6">  
    <h2 class="text-2xl font-bold mb-1">Create Account</h2>  
    <p class="text-gray-400 mb-6">Join Wilson Desire Hub</p>  
    <div class="space-y-4">  
      <div><label class="text-sm">Full Name</label><input id="reg-name" type="text" placeholder="Enter your full name" class="w-full p-3 mt-1 rounded-lg bg-gray-800 border border-gray-700"></div>  
      <div><label class="text-sm">Phone Number</label><input id="reg-phone" type="tel" placeholder="099... or 088..." class="w-full p-3 mt-1 rounded-lg bg-gray-800 border border-gray-700"></div>  
      <div><label class="text-sm">Password</label><input id="reg-pass" type="password" placeholder="Create a password" class="w-full p-3 mt-1 rounded-lg bg-gray-800 border border-gray-700"></div>  
      <button onclick="registerUser()" class="yellow-btn w-full py-3 rounded-lg mt-4">Register</button>  
      <p class="text-center text-sm text-gray-400 mt-4">Already have an account? <span onclick="showScreen('login')" class="text-yellow-400 cursor-pointer">Login</span></p>  
    </div>  
  </div>    <!-- SCREEN 3: LOGIN -->    <div id="login" class="app-screen p-6">  
    <h2 class="text-2xl font-bold mb-1">Welcome Back!</h2>  
    <p class="text-gray-400 mb-6">Login to your account</p>  
    <div class="space-y-4">  
      <div><label class="text-sm">Phone Number</label><input id="login-phone" type="tel" placeholder="Enter your phone number" class="w-full p-3 mt-1 rounded-lg bg-gray-800 border border-gray-700"></div>  
      <div><label class="text-sm">Password</label><input id="login-pass" type="password" placeholder="Enter your password" class="w-full p-3 mt-1 rounded-lg bg-gray-800 border border-gray-700"></div>  
      <button onclick="loginUser()" class="yellow-btn w-full py-3 rounded-lg">Login</button>  
    </div>  
  </div>    <!-- SCREEN 4: HOME -->    <div id="home" class="app-screen pb-20">  
    <div class="p-4">  
      <div class="flex justify-between items-center mb-4">  
        <div><p class="text-gray-400 text-sm">Good Morning!</p><h2 id="home-username" class="text-xl font-bold">Wilson Desire</h2></div>  
        <i class="fa-regular fa-bell text-xl"></i>  
      </div>  
      <div class="relative mb-4">  
        <input type="text" placeholder="Search for products, services..." class="w-full p-3 pl-10 rounded-lg bg-gray-800 border border-gray-700">  
        <i class="fa fa-search absolute left-3 top-4 text-gray-400"></i>  
      </div>  
      <div class="card-dark p-4 rounded-lg mb-4">  
        <h3 class="font-bold mb-1">SUPPORT LOCAL BUSINESSES</h3>  
        <p class="text-sm text-gray-300">Buy Malawi, Build Malawi</p>  
      </div>  
      <h3 class="font-bold mb-3">Top Categories</h3>  
      <div class="grid grid-cols-4 gap-3 mb-4">  
        <div onclick="showScreen('market')" class="text-center cursor-pointer">  
          <div class="card-dark p-3 rounded-lg mb-1"><i class="fa fa-mobile text-xl text-yellow-400"></i></div><p class="text-xs">Phones</p>  
        </div>  
        <div onclick="showScreen('market')" class="text-center cursor-pointer">  
          <div class="card-dark p-3 rounded-lg mb-1"><i class="fa fa-shirt text-xl text-yellow-400"></i></div><p class="text-xs">Fashion</p>  
        </div>  
        <div onclick="showScreen('services')" class="text-center cursor-pointer">  
          <div class="card-dark p-3 rounded-lg mb-1"><i class="fa fa-screwdriver-wrench text-xl text-yellow-400"></i></div><p class="text-xs">Services</p>  
        </div>  
        <div onclick="showScreen('aihub')" class="text-center cursor-pointer">  
          <div class="card-dark p-3 rounded-lg mb-1"><i class="fa fa-robot text-xl text-yellow-400"></i></div><p class="text-xs">AI Hub</p>  
        </div>  
      </div>  
    </div>  
  </div>    <!-- SCREEN 5: MARKET - IKUGWIRA -->    <div id="market" class="app-screen pb-20 p-4">  
    <h2 class="text-xl font-bold mb-4">Market</h2>  
    <div class="flex gap-2 mb-4 overflow-x-auto">  
      <button onclick="filterMarket('all')" class="yellow-btn px-4 py-1 rounded-full text-sm">All</button>  
      <button onclick="filterMarket('phone')" class="card-dark px-4 py-1 rounded-full text-sm">Phones</button>  
      <button onclick="filterMarket('fashion')" class="card-dark px-4 py-1 rounded-full text-sm">Fashion</button>  
      <button onclick="filterMarket('electronic')" class="card-dark px-4 py-1 rounded-full text-sm">Electronics</button>  
    </div>  
    <div id="market-grid" class="grid grid-cols-2 gap-4">  
      <!-- Products zizadzadza ndi JS -->  
    </div>  
  </div>    <!-- SCREEN 6: SERVICES - IKUGWIRA -->    <div id="services" class="app-screen pb-20 p-4">  
    <h2 class="text-xl font-bold mb-4">Services</h2>  
    <div class="space-y-3">  
      <div onclick="bookService('Delivery Services')" class="card-dark p-4 rounded-lg flex items-center gap-4 cursor-pointer">  
        <div class="bg-yellow-400 p-3 rounded-lg"><i class="fa fa-motorcycle text-black text-xl"></i></div>  
        <div class="flex-1"><p class="font-bold">Delivery Services</p><p class="text-sm text-gray-400">Fast delivery in Lilongwe & Blantyre</p></div>  
        <i class="fa fa-chevron-right text-gray-400"></i>  
      </div>  
      <div onclick="bookService('Phone Repair')" class="card-dark p-4 rounded-lg flex items-center gap-4 cursor-pointer">  
        <div class="bg-yellow-400 p-3 rounded-lg"><i class="fa fa-screwdriver-wrench text-black text-xl"></i></div>  
        <div class="flex-1"><p class="font-bold">Phone Repair</p><p class="text-sm text-gray-400">Screen, battery & software fix</p></div>  
        <i class="fa fa-chevron-right text-gray-400"></i>  
      </div>  
      <div onclick="bookService('Graphic Design')" class="card-dark p-4 rounded-lg flex items-center gap-4 cursor-pointer">  
        <div class="bg-yellow-400 p-3 rounded-lg"><i class="fa fa-paintbrush text-black text-xl"></i></div>  
        <div class="flex-1"><p class="font-bold">Graphic Design</p><p class="text-sm text-gray-400">Logos, posters & social media</p></div>  
        <i class="fa fa-chevron-right text-gray-400"></i>  
      </div>  
      <div onclick="bookService('Car Hire')" class="card-dark p-4 rounded-lg flex items-center gap-4 cursor-pointer">  
        <div class="bg-yellow-400 p-3 rounded-lg"><i class="fa fa-car text-black text-xl"></i></div>  
        <div class="flex-1"><p class="font-bold">Car Hire</p><p class="text-sm text-gray-400">Self-drive & with driver</p></div>  
        <i class="fa fa-chevron-right text-gray-400"></i>  
      </div>  
    </div>  
  </div>    <!-- SCREEN 7: AI HUB - IKUGWIRA -->    <div id="aihub" class="app-screen pb-20 p-4">  
    <h2 class="text-xl font-bold mb-4">AI Hub</h2>  
    <div class="grid grid-cols-2 gap-4 mb-4">  
      <div onclick="openAITool('AI Chat')" class="card-dark p-4 rounded-lg text-center cursor-pointer">  
        <i class="fa fa-comments text-3xl text-yellow-400 mb-2"></i><p class="font-bold text-sm">AI Chat</p><p class="text-xs text-gray-400">Ask in Chichewa</p>  
      </div>  
      <div onclick="openAITool('Image Creator')" class="card-dark p-4 rounded-lg text-center cursor-pointer">  
        <i class="fa fa-image text-3xl text-yellow-400 mb-2"></i><p class="font-bold text-sm">Image Creator</p><p class="text-xs text-gray-400">Generate pictures</p>  
      </div>  
      <div onclick="openAITool('CV Builder')" class="card-dark p-4 rounded-lg text-center cursor-pointer">  
        <i class="fa fa-file-lines text-3xl text-yellow-400 mb-2"></i><p class="font-bold text-sm">CV Builder</p><p class="text-xs text-gray-400">Make professional CV</p>  
      </div>  
      <div onclick="openAITool('Translator')" class="card-dark p-4 rounded-lg text-center cursor-pointer">  
        <i class="fa fa-language text-3xl text-yellow-400 mb-2"></i><p class="font-bold text-sm">Translator</p><p class="text-xs text-gray-400">Chichewa to English</p>  
      </div>  
    </div>  
    <div class="card-dark p-4 rounded-lg">  
      <p class="font-bold mb-2">AI Chat</p>  
      <div id="chat-box" class="bg-gray-800 p-3 rounded-lg mb-2 h-40 overflow-y-auto">  
        <p class="text-sm"><span class="text-yellow-400">AI:</span> Muli bwanji? Ndine AI wanu. Ndingakuthandizeni chani lero?</p>  
      </div>  
      <div class="flex gap-2">  
        <input id="chat-input" type="text" placeholder="Lembani apa..." class="flex-1 p-2 rounded-lg bg-gray-800 border border-gray-700 text-sm">  
        <button onclick="sendChat()" class="yellow-btn px-4 rounded-lg"><i class="fa fa-paper-plane"></i></button>  
      </div>  
    </div>  
  </div>    <!-- SCREEN 8: PROFILE - IKUGWIRA -->    <div id="profile" class="app-screen pb-20 p-4">  
    <div class="text-center mb-6">  
      <div class="w-20 h-20 bg-yellow-400 rounded-full mx-auto mb-3 flex items-center justify-center">  
        <i class="fa fa-user text-3xl text-black"></i>  
      </div>  
      <h2 id="profile-name" class="text-xl font-bold">Wilson Desire</h2>  
      <p id="profile-phone" class="text-gray-400 text-sm">+265 991 234 567</p>  
    </div>  <div class="space-y-3">  
  <div onclick="showAlert('Wallet: MK 25,000')" class="card-dark p-4 rounded-lg flex items-center justify-between cursor-pointer">  
    <div class="flex items-center gap-3"><i class="fa fa-wallet text-yellow-400"></i><p class="font-semibold">My Wallet</p></div>  
    <p class="text-yellow-400 font-bold">MK 25,000</p>  
  </div>  
  <div onclick="showAlert('You have 3 orders')" class="card-dark p-4 rounded-lg flex items-center gap-3 cursor-pointer">  
    <i class="fa fa-bag-shopping text-yellow-400"></i><p class="font-semibold">My Orders</p>  
  </div>  
  <div onclick="showAlert('Wishlist is empty')" class="card-dark p-4 rounded-lg flex items-center gap-3 cursor-pointer">  
    <i class="fa fa-heart text-yellow-400"></i><p class="font-semibold">Wishlist</p>  
  </div>  
  <div onclick="showAlert('Settings coming soon')" class="card-dark p-4 rounded-lg flex items-center gap-3 cursor-pointer">  
    <i class="fa fa-gear text-yellow-400"></i><p class="font-semibold">Settings</p>  
  </div>  
  <div onclick="showAlert('Call: 0999123456 for help')" class="card-dark p-4 rounded-lg flex items-center gap-3 cursor-pointer">  
    <i class="fa fa-circle-question text-yellow-400"></i><p class="font-semibold">Help & Support</p>  
  </div>  
  <button onclick="logout()" class="w-full mt-6 border border-red-500 text-red-500 py-3 rounded-lg">  
    <i class="fa fa-right-from-bracket mr-2"></i>Logout  
  </button>  
</div>

  </div>    <!-- PRODUCT MODAL -->    <div id="product-modal" class="modal fixed inset-0 bg-black bg-opacity-70 items-center justify-center p-4 z-50">  
    <div class="card-dark rounded-lg p-4 w-full max-w-sm">  
      <div class="flex justify-between items-center mb-3">  
        <h3 id="modal-title" class="text-lg font-bold"></h3>  
        <i onclick="closeModal()" class="fa fa-times cursor-pointer"></i>  
      </div>  
      <img id="modal-img" src="" class="w-full h-48 object-cover rounded mb-3" alt="">  
      <p id="modal-price" class="text-yellow-400 font-bold text-xl mb-3"></p>  
      <p id="modal-desc" class="text-sm text-gray-300 mb-4"></p>  
      <button onclick="addToCart()" class="yellow-btn w-full py-3 rounded-lg">Add to Cart</button>  
    </div>  
  </div>    <!-- BOTTOM NAV -->    <div id="bottom-nav" class="fixed bottom-0 left-0 right-0 bg-gray-900 border-t border-gray-800 flex justify-around py-3" style="display: none;">  
    <button onclick="showScreen('home')" id="nav-home" class="text-center text-gray-400">  
      <i class="fa fa-home"></i><p class="text-xs">Home</p>  
    </button>  
    <button onclick="showScreen('market')" id="nav-market" class="text-center text-gray-400">  
      <i class="fa fa-store"></i><p class="text-xs">Market</p>  
    </button>  
    <button onclick="showScreen('services')" id="nav-services" class="text-center text-gray-400">  
      <i class="fa fa-th-large"></i><p class="text-xs">Services</p>  
    </button>  
    <button onclick="showScreen('aihub')" id="nav-aihub" class="text-center text-gray-400">  
      <i class="fa fa-robot"></i><p class="text-xs">AI Hub</p>  
    </button>  
    <button onclick="showScreen('profile')" id="nav-profile" class="text-center text-gray-400">  
      <i class="fa fa-user"></i><p class="text-xs">Profile</p>  
    </button>  
  </div>  <script>  
let currentUser = { name: "Wilson Desire", phone: "+265 991 234 567" };  
  
const products = [  
  { id: 1, name: "Samsung A14", price: "MK 179,999", img: "https://images.unsplash.com/photo-1592899670303-95339c9b78f2?w=300", cat: "phone", desc: "128GB, 4GB RAM, Dual SIM. Brand new with warranty." },  
  { id: 2, name: "Men's Hoodie", price: "MK 15,000", img: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?w=300", cat: "fashion", desc: "Cotton hoodie, available in Black, Grey, Navy. Size M-XL" },  
  { id: 3, name: "Sony Headphones", price: "MK 45,000", img: "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=300", cat: "electronic", desc: "Wireless Bluetooth, Noise Cancelling, 20hrs battery" },  
  { id: 4, name: "Cotton T-Shirt", price: "MK 8,500", img: "https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?w=300", cat: "fashion", desc: "100% Cotton, Malawi made. All colors available" },  
  { id: 5, name: "iPhone 13", price: "MK 650,000", img: "https://images.unsplash.com/photo-1591337676887-a217a6970a8a?w=300", cat: "phone", desc: "256GB, UK Used, Battery 90%, No scratches" },  
  { id: 6, name: "Laptop Stand", price: "MK 12,000", img: "https://images.unsplash.com/photo-1527864550417-7fd91fc51a46?w=300", cat: "electronic", desc: "Aluminum, adjustable, fits 10-17 inch laptops" }  
];  
  
function showScreen(screenId) {  
  document.querySelectorAll('.app-screen').forEach(screen => screen.classList.remove('active'));  
  document.getElementById(screenId).classList.add('active');  
    
  const navScreens = ['home', 'market', 'services', 'aihub', 'profile'];  
  document.getElementById('bottom-nav').style.display = navScreens.includes(screenId) ? 'flex' : 'none';  
    
  document.querySelectorAll('[id^="nav-"]').forEach(btn => {  
    btn.classList.remove('nav-active');  
    btn.classList.add('text-gray-400');  
  });  
  const activeNav = document.getElementById('nav-' + screenId);  
  if(activeNav) {  
    activeNav.classList.add('nav-active');  
    activeNav.classList.remove('text-gray-400');  
  }  
    
  if(screenId === 'market') loadMarket();  
  window.scrollTo(0, 0);  
}  
  
function registerUser() {  
  const name = document.getElementById('reg-name').value;  
  const phone = document.getElementById('reg-phone').value;  
  if(name && phone) {  
    currentUser = { name, phone };  
    document.getElementById('home-username').innerText = name;  
    document.getElementById('profile-name').innerText = name;  
    document.getElementById('profile-phone').innerText = phone;  
    showScreen('home');  
  } else {  
    alert('Chonde lembani dzina ndi nambala');  
  }  
}  
  
function loginUser() {  
  const phone = document.getElementById('login-phone').value;  
  if(phone) {  
    showScreen('home');  
  } else {  
    alert('Lowetsani nambala ya foni');  
  }  
}  
  
function logout() {  
  showScreen('welcome');  
}  
  
function loadMarket(filter = 'all') {  
  const grid = document.getElementById('market-grid');  
  grid.innerHTML = '';  
  const filtered = filter === 'all' ? products : products.filter(p => p.cat === filter);  
    
  filtered.forEach(p => {  
    grid.innerHTML += `  
      <div onclick="openProduct(${p.id})" class="card-dark rounded-lg p-2 cursor-pointer">  
        <img src="${p.img}" class="w-full h-32 object-cover rounded mb-2" alt="${p.name}">  
        <p class="text-sm font-semibold">${p.name}</p>  
        <p class="text-yellow-400 font-bold">${p.price}</p>  
      </div>  
    `;  
  });  
}  
  
function filterMarket(cat) {  
  loadMarket(cat);  
}  
  
function openProduct(id) {  
  const p = products.find(x => x.id === id);  
  document.getElementById('modal-title').innerText = p.name;  
  document.getElementById('modal-img').src = p.img;  
  document.getElementById('modal-price').innerText = p.price;  
  document.getElementById('modal-desc').innerText = p.desc;  
  document.getElementById('product-modal').classList.add('active');  
}  
  
function closeModal() {  
  document.getElementById('product-modal').classList.remove('active');  
}  
  
function addToCart() {  
  alert('Zawonjezedwa ku Cart! ✅');  
  closeModal();  
}  
  
function bookService(name) {  
  alert(name + ' - Tabooka! Tikulumikizana nanu posachedwa 📞');  
}  
  
function openAITool(tool) {  
  alert(tool + ' ikubwera posachedwa! 🤖');  
}  
  
function sendChat() {  
  const input = document.getElementById('chat-input');  
  const chatBox = document.getElementById('chat-box');  
  if(input.value.trim()) {  
    chatBox.innerHTML += `<p class="text-sm mt-2"><span class="text-blue-400">Inu:</span> ${input.value}</p>`;  
    chatBox.in
