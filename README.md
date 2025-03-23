111
112
113
114
115
116
117
118
119
120
121
122
123
124
125
126
127
128
129
130
131
132
133
134
135
136
137
138
139
140
141
142
143
144
145
146
147
148
149
150
151
152
153
154
155
156
157
158
159
160
161
162
163
164
165
166
167
168
169
170
171
172
173
174
175
176
177
178
179
180
181
182
183
184
185
186
187
188
189
190
191
<!DOCTYPE html>
            color: white;
            padding: 12px;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#shop">Shop</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    <header>
        <div class="hero">
            <h1>Welcome to Our Store</h1>
            <p>Exclusive streetwear at unbeatable prices</p>
        </div>
    </header>
    
    <section id="shop">
        <h2>Shop</h2>
        <div class="product">
            <img src="product1.jpg" alt="Product 1">
            <h2>Streetwear Hoodie</h2>
            <p>$49.99</p>
            <button onclick="addToCart('Streetwear Hoodie', 49.99)">Add to Cart</button>
        </div>
        <div class="product">
            <img src="product2.jpg" alt="Product 2">
            <h2>Urban T-Shirt</h2>
            <p>$29.99</p>
            <button onclick="addToCart('Urban T-Shirt', 29.99)">Add to Cart</button>
        </div>
    </section>
    
    <section class="cart">
        <h2>Shopping Cart</h2>
        <ul class="cart-items"></ul>
        <p>Total: $<span id="total">0.00</span></p>
        <button class="checkout" onclick="checkout()">Checkout</button>
    </section>
    
    <footer>
        <p>&copy; 2025 Slime Streetwear. All rights reserved.</p>
    </footer>
    
    <script>
        let cart = [];

        function addToCart(name, price) {
            cart.push({ name, price });
            updateCart();
        }

        function updateCart() {
            const cartItems = document.querySelector('.cart-items');
            cartItems.innerHTML = '';
            let total = 0;
            cart.forEach((item, index) => {
                total += item.price;
                cartItems.innerHTML += `<li>${item.name} - $${item.price.toFixed(2)} <button onclick="removeFromCart(${index})">Remove</button></li>`;
            });
            document.getElementById('total').textContent = total.toFixed(2);
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCart();
        }

        function checkout() {
            alert('Checkout process initiated!');
        }
    </script>
</body>
</html>
