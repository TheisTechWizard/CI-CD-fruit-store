<template>
    <div class="landing-page">
        <!-- Hero Section -->
        <section class="hero">
            <div class="hero-content">
                <h1>Fresh & Delicious Fruits</h1>
                <p>Discover nature's sweetest treasures</p>
                <button class="cta-button">Shop Now</button>
            </div>
        </section>

        <!-- Featured Products -->
        <section class="featured-products">
            <h2>Featured Products</h2>
            <div class="product-grid">
                <div v-for="(product, index) in featuredProducts" :key="index" class="product-card">
                    <div class="product-image" :style="{ backgroundColor: product.color }">
                        <span class="product-icon">{{ product.icon }}</span>
                    </div>
                    <h3>{{ product.name }}</h3>
                    <p>{{ product.price }}</p>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section class="about-section">
            <div class="about-content">
                <h2>About Our Store</h2>
                <p>We source the freshest fruits from local farmers and international suppliers to bring you the best
                    quality produce. Our commitment to quality and sustainability makes us your trusted fruit
                    destination.</p>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact-section">
            <h2>Get in Touch</h2>
            <div class="contact-grid">
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    <p>📍 123 Fruit Street, Fresh City</p>
                    <p>📞 (555) 123-4567</p>
                    <p>✉️ hello@fruitstore.com</p>
                </div>
                <form class="contact-form">
                    <input type="text" placeholder="Your Name" />
                    <input type="email" placeholder="Your Email" />
                    <textarea placeholder="Your Message"></textarea>
                    <button type="submit" class="submit-button">Send Message</button>
                </form>
            </div>
        </section>
    </div>
</template>

<script>
export default {
    name: 'LandingPage',
    data() {
        return {
            featuredProducts: [
                { name: 'Organic Apples', price: '$4.99/lb', icon: '🍎', color: '#ffebee' },
                { name: 'Fresh Oranges', price: '$3.99/lb', icon: '🍊', color: '#fff3e0' },
                { name: 'Sweet Bananas', price: '$2.99/lb', icon: '🍌', color: '#fffde7' },
                { name: 'Juicy Strawberries', price: '$5.99/lb', icon: '🍓', color: '#fce4ec' }
            ]
        }
    }
}
</script>

<style scoped>
.landing-page {
    font-family: 'Inter', sans-serif;
}

.hero {
    height: 80vh;
    background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
        url('https://images.unsplash.com/photo-1610832958506-aa56368176cf?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80');
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: white;
}

.hero-content {
    max-width: 800px;
    padding: 2rem;
}

.hero h1 {
    font-size: 4rem;
    margin-bottom: 1rem;
    font-weight: 700;
}

.hero p {
    font-size: 1.5rem;
    margin-bottom: 2rem;
}

.cta-button {
    padding: 1rem 2rem;
    font-size: 1.2rem;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

.cta-button:hover {
    background-color: #45a049;
}

.featured-products {
    padding: 5rem 2rem;
    text-align: center;
}

.featured-products h2 {
    font-size: 2.5rem;
    margin-bottom: 3rem;
}

.product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

.product-card {
    background: white;
    border-radius: 10px;
    padding: 1.5rem;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s;
}

.product-card:hover {
    transform: translateY(-5px);
}

.product-image {
    height: 150px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1rem;
}

.product-icon {
    font-size: 4rem;
}

.product-card h3 {
    margin: 1rem 0;
    font-size: 1.2rem;
}

.add-to-cart {
    background-color: #4CAF50;
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

.add-to-cart:hover {
    background-color: #45a049;
}

.about-section {
    background-color: #f9f9f9;
    padding: 5rem 2rem;
    text-align: center;
}

.about-content {
    max-width: 800px;
    margin: 0 auto;
}

.about-section h2 {
    font-size: 2.5rem;
    margin-bottom: 2rem;
}

.contact-section {
    padding: 5rem 2rem;
    text-align: center;
}

.contact-section h2 {
    font-size: 2.5rem;
    margin-bottom: 3rem;
}

.contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 3rem;
    max-width: 1200px;
    margin: 0 auto;
}

.contact-info {
    text-align: left;
}

.contact-form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.contact-form input,
.contact-form textarea {
    padding: 1rem;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 1rem;
}

.contact-form textarea {
    height: 150px;
    resize: vertical;
}

.submit-button {
    background-color: #4CAF50;
    color: white;
    border: none;
    padding: 1rem;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1rem;
    transition: background-color 0.3s;
}

.submit-button:hover {
    background-color: #45a049;
}

@media (max-width: 768px) {
    .hero h1 {
        font-size: 2.5rem;
    }

    .hero p {
        font-size: 1.2rem;
    }

    .product-grid {
        grid-template-columns: 1fr;
    }
}
</style>