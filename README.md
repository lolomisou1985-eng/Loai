<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>عزيزة طوبال | AzizaToubal Haute Couture</title>
    <!-- Tailwind CSS for modern styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Professional Arabic and English Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Playfair+Display:wght@400;700&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #c5a059;
            --gold-light: #e2c285;
            --dark-gold: #8e6d2f;
            --cream: #fbf9f6;
            --rich-black: #1a1a1a;
        }
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: var(--cream);
            color: var(--rich-black);
            overflow-x: hidden;
        }
        .luxury-font { font-family: 'Playfair Display', serif; }
        .arabic-luxury { font-family: 'Amiri', serif; }
        
        /* Arabesque pattern background */
        .hero-pattern {
            background-image: url("https://www.transparenttextures.com/patterns/arabesque.png");
            background-attachment: fixed;
        }

        .gold-gradient {
            background: linear-gradient(135deg, var(--dark-gold), var(--gold), var(--gold-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .btn-gold {
            background: linear-gradient(135deg, var(--dark-gold), var(--gold));
            transition: all 0.3s ease;
        }
        .btn-gold:hover {
            transform: scale(1.02);
            box-shadow: 0 10px 20px rgba(142, 109, 47, 0.2);
        }

        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: 2000;
            background: rgba(0,0,0,0.85);
            backdrop-filter: blur(10px);
        }
        .modal-content {
            position: absolute;
            top: 50%; left: 50%;
            transform: translate(-50%, -50%);
            width: 95%;
            max-width: 650px;
            max-height: 90vh;
            overflow-y: auto;
            background: white;
            border-radius: 40px;
            padding: 2.5rem;
        }

        .input-luxury {
            border: 1px solid #e5e7eb;
            padding: 1rem;
            border-radius: 12px;
            width: 100%;
            margin-bottom: 1.25rem;
            transition: all 0.3s;
        }
        .input-luxury:focus {
            border-color: var(--gold);
            outline: none;
            box-shadow: 0 0 0 3px rgba(197, 160, 89, 0.1);
        }

        .chip {
            cursor: pointer;
            border: 1px solid #eee;
            padding: 0.6rem 1.2rem;
            border-radius: 50px;
            font-size: 0.9rem;
            transition: all 0.3s;
        }
        .chip.active {
            background: var(--gold);
            color: white;
            border-color: var(--gold);
        }
    </style>
</head>
<body class="hero-pattern">

    <!-- Header Section -->
    <header class="bg-white/90 backdrop-blur-md sticky top-0 z-[1000] border-b border-gold/10 py-6">
        <div class="container mx-auto px-4 flex flex-col items-center">
            <h1 class="arabic-luxury text-5xl md:text-7xl font-bold gold-gradient">AzizaToubal</h1>
            <p class="luxury-font text-xs tracking-[0.5em] text-gray-500 uppercase mt-2">Haute Couture</p>
            
            <nav class="mt-6 flex gap-6 text-[10px] font-bold tracking-widest text-gray-400">
                <a href="#" id="head-ig" target="_blank" class="hover:text-gold transition">INSTAGRAM</a>
                <span>/</span>
                <a href="#" id="head-wa" target="_blank" class="hover:text-gold transition">WHATSAPP</a>
            </nav>
        </div>
    </header>

    <main class="container mx-auto px-4 py-16">
        <!-- Hero Intro -->
        <div class="text-center max-w-3xl mx-auto mb-20">
            <h2 class="text-3xl md:text-5xl font-light mb-6">مجموعة <span class="font-bold italic">الأصالة</span> الجزائرية</h2>
            <p class="text-gray-500 leading-relaxed italic">تصاميم يدوية فاخرة تجمع بين عراقة الماضي وأناقة الحاضر.</p>
            <div class="h-0.5 w-20 bg-gold mx-auto mt-8 opacity-40"></div>
        </div>

        <!-- Admin Access (Simple Button) -->
        <div class="flex justify-end mb-6">
            <button onclick="openAdmin()" class="text-[10px] font-bold text-gold border-b border-gold/30 pb-1">إعدادات المتجر</button>
        </div>

        <!-- Product Grid -->
        <div id="product-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
            <!-- Products injected by JavaScript -->
        </div>
    </main>

    <!-- Reservation Modal -->
    <div id="order-modal" class="modal">
        <div class="modal-content">
            <div class="text-center mb-8">
                <h3 class="arabic-luxury text-3xl text-gold mb-2">إتمام الحجز</h3>
                <p class="text-xs text-gray-400">سيتم إرسال تفاصيل الطلب مباشرة لواتساب الأتيليه</p>
            </div>
            
            <div class="space-y-4">
                <input type="text" id="order-name" class="input-luxury" placeholder="الاسم الكامل للزبونة">
                <input type="tel" id="order-phone" class="input-luxury" placeholder="رقم الهاتف">
                
                <select id="order-wilaya" class="input-luxury">
                    <option value="">اختر الولاية (58 ولاية)</option>
                    <script>
                        const wilayas = ["أدرار", "الشلف", "الأغواط", "أم البواقي", "باتنة", "بجاية", "بسكرة", "بشار", "البليدة", "البويرة", "تمنراست", "تبسة", "تلمسان", "تيارت", "تيزي وزو", "الجزائر العاصمة", "الجلفة", "جيجل", "سطيف", "سعيدة", "سكيكدة", "سيدي بلعباس", "عنابة", "قالمة", "قسنطينة", "المدية", "مستغانم", "المسيلة", "معسكر", "ورقلة", "وهران", "البيض", "إليزي", "برج بوعريريج", "بومرداس", "الطارف", "تندوف", "تيسمسيلت", "الوادي", "خنشلة", "سوق أهراس", "تيبازة", "ميلة", "عين الدفلى", "النعامة", "عين تموشنت", "غرداية", "غليزان", "تيميمون", "برج باجي مختار", "أولاد جلال", "بني عباس", "عين صالح", "عين قزام", "تقرت", "جانت", "المغير", "المنيعة"];
                        wilayas.forEach((w, i) => {
                            document.write(`<option value="${(i+1).toString().padStart(2, '0')}-${w}">${(i+1).toString().padStart(2, '0')} - ${w}</option>`);
                        });
                    </script>
                </select>

                <div class="bg-gray-50 p-6 rounded-2xl">
                    <p class="text-[10px] font-bold text-gray-400 mb-3 uppercase tracking-widest">المقاس</p>
                    <div id="size-options" class="flex flex-wrap gap-2 mb-6"></div>
                    
                    <p class="text-[10px] font-bold text-gray-400 mb-3 uppercase tracking-widest">اللون المفضل</p>
                    <div id="color-options" class="flex flex-wrap gap-2"></div>
                </div>

                <button onclick="confirmAndSend()" class="w-full btn-gold text-white py-4 rounded-xl font-bold shadow-lg mt-6">تأكيد الطلب عبر واتساب</button>
                <button onclick="closeModals()" class="w-full text-gray-400 text-xs mt-4">إلغاء</button>
            </div>
        </div>
    </div>

    <!-- Admin Modal -->
    <div id="admin-modal" class="modal">
        <div class="modal-content">
            <h3 class="text-xl font-bold mb-6">إدارة المتجر</h3>
            <div class="space-y-4">
                <input type="text" id="admin-phone" class="input-luxury" placeholder="رقم الواتساب (مثال: 213550000000)">
                <input type="text" id="admin-ig" class="input-luxury" placeholder="رابط إنستغرام">
                <hr>
                <p class="font-bold text-sm">إضافة موديل جديد:</p>
                <input type="text" id="new-name" class="input-luxury" placeholder="اسم الفستان">
                <input type="text" id="new-price" class="input-luxury" placeholder="السعر (مثال: 95,000 دج)">
                <input type="text" id="new-img" class="input-luxury" placeholder="رابط صورة الفستان">
                <input type="text" id="new-colors" class="input-luxury" placeholder="الألوان المتاحة (فصلها بفاصلة)">
                <button onclick="addNewProduct()" class="w-full bg-black text-white py-3 rounded-lg">إضافة الموديل</button>
            </div>
            <div id="edit-list" class="mt-8 space-y-2"></div>
            <button onclick="saveAdminAndClose()" class="w-full mt-6 btn-gold text-white py-3 rounded-lg font-bold">حفظ وإغلاق</button>
        </div>
    </div>

    <footer class="py-20 text-center opacity-40">
        <p class="arabic-luxury text-2xl mb-2">AzizaToubal</p>
        <p class="text-[10px] tracking-[1em]">MADE IN ALGERIA</p>
    </footer>

    <script>
        let config = {
            phone: "213550000000",
            instagram: "https://instagram.com/",
            products: [
                { id: 1, name: "كاراكو عاصمي 'مريم'", price: "110,000 دج", img: "https://images.unsplash.com/photo-1566174053879-31528523f8ae?auto=format&fit=crop&q=80&w=1000", colors: ["أبيض", "ذهبي"] },
                { id: 2, name: "قفطان ملكي 'سلطانة'", price: "85,000 دج", img: "https://images.unsplash.com/photo-1595777457583-95e059d581b8?auto=format&fit=crop&q=80&w=1000", colors: ["أزرق", "فضي"] }
            ],
            sizes: ["36", "38", "40", "42", "44", "46"]
        };

        let currentOrder = null;
        let selectedSize = '';
        let selectedColor = '';

        function renderProducts() {
            document.getElementById('head-ig').href = config.instagram;
            document.getElementById('head-wa').href = `https://wa.me/${config.phone}`;
            const grid = document.getElementById('product-grid');
            grid.innerHTML = '';
            config.products.forEach(p => {
                grid.innerHTML += `
                    <div class="bg-white rounded-[2rem] overflow-hidden shadow-sm border border-gold/5 flex flex-col">
                        <img src="${p.img}" class="h-96 w-full object-cover">
                        <div class="p-8 text-center flex-grow flex flex-col justify-between">
                            <div>
                                <h3 class="text-xl font-bold mb-2">${p.name}</h3>
                                <p class="text-gold font-bold mb-6">${p.price}</p>
                            </div>
                            <button onclick="openOrder(${p.id})" class="btn-gold text-white w-full py-4 rounded-xl font-bold">طلب حجز</button>
                        </div>
                    </div>
                `;
            });
        }

        function openOrder(id) {
            currentOrder = config.products.find(p => p.id === id);
            selectedSize = ''; selectedColor = '';
            document.getElementById('order-modal').style.display = 'block';
            const sDiv = document.getElementById('size-options');
            sDiv.innerHTML = config.sizes.map(s => `<div class="chip size-item" onclick="selectOption(this, 'size', '${s}')">${s}</div>`).join('');
            const cDiv = document.getElementById('color-options');
            cDiv.innerHTML = currentOrder.colors.map(c => `<div class="chip color-item" onclick="selectOption(this, 'color', '${c}')">${c}</div>`).join('');
        }

        function selectOption(el, type, val) {
            document.querySelectorAll(`.${type}-item`).forEach(i => i.classList.remove('active'));
            el.classList.add('active');
            if(type === 'size') selectedSize = val; else selectedColor = val;
        }

        function confirmAndSend() {
            const name = document.getElementById('order-name').value;
            const phone = document.getElementById('order-phone').value;
            const wilaya = document.getElementById('order-wilaya').value;
            if(!name || !phone || !wilaya || !selectedSize || !selectedColor) { alert("أكملي البيانات من فضلكِ"); return; }
            const msg = `طلب حجز جديد من الموقع:\nالاسم: ${name}\nالهاتف: ${phone}\nالولاية: ${wilaya}\nالموديل: ${currentOrder.name}\nالمقاس: ${selectedSize}\nاللون: ${selectedColor}`;
            window.open(`https://wa.me/${config.phone}?text=${encodeURIComponent(msg)}`, '_blank');
            closeModals();
        }

        function openAdmin() {
            document.getElementById('admin-phone').value = config.phone;
            document.getElementById('admin-ig').value = config.instagram;
            const list = document.getElementById('edit-list');
            list.innerHTML = config.products.map((p, i) => `<div class="flex justify-between text-xs p-2 bg-gray-50 rounded"><span>${p.name}</span><button onclick="deleteP(${i})" class="text-red-500">حذف</button></div>`).join('');
            document.getElementById('admin-modal').style.display = 'block';
        }

        function addNewProduct() {
            const n = document.getElementById('new-name').value;
            const p = document.getElementById('new-price').value;
            const im = document.getElementById('new-img').value;
            const c = document.getElementById('new-colors').value.split(',').map(x => x.trim());
            if(n && p && im) { config.products.unshift({id: Date.now(), name: n, price: p, img: im, colors: c}); openAdmin(); }
        }

        function deleteP(i) { config.products.splice(i, 1); openAdmin(); }
        function saveAdminAndClose() { config.phone = document.getElementById('admin-phone').value; config.instagram = document.getElementById('admin-ig').value; renderProducts(); closeModals(); }
        function closeModals() { document.querySelectorAll('.modal').forEach(m => m.style.display = 'none'); }
        window.onload = renderProducts;
    </script>
</body>
</html>
