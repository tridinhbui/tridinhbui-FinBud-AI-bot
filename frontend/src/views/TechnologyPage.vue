<template>
  <div class="features-container">
    <h2 class="features-title animate fade-in">Analytics that drive your business.</h2>
    <p class="description animate fade-in">Review your performance and drive change with our actionable insights provided via our intuitive web app.</p>
    <div class="feature-grid">
      <div class="feature animate slide-in-left" v-for="feature in features" :key="feature.id">
        <div class="feature-icon-title">
          <img src="@/assets/tick.png" alt="Tick" class="tick-icon" />
          <h3 class="feature-title">{{ feature.title }}</h3>
        </div>
        <p class="feature-description">{{ feature.description }}</p>
      </div>
    </div>
    <div class="insights-section">
      <div class="image animate slide-in-right">
        <img src="@/assets/stock.png" alt="Car in garage">
      </div>
      <div class="content animate slide-in-left">
        <h2>ARTIFICIAL INTELLIGENCE</h2>
        <h3>Get real-time insights on your performance.</h3>
        <p>Empower your financial decisions with our cutting-edge AI technology.</p>
        <div class="list-item">
          <img src= "@/assets/tick.png" alt="Check">
          <span>Personalized Financial Analysis: Gain comprehensive insights with auto-generated reports tailored to your financial behavior, helping you optimize your budget and savings.</span>
        </div>
        <div class="list-item">
          <img src="@/assets/tick.png"  alt="Check">
          <span>Trend Prediction: Our AI-driven tools analyze past spending and earning trends to forecast your financial future, enabling proactive financial planning.</span>
        </div>
        <button @click="learnMore" class="animate slide-in-up">Learn more</button>
      </div>
    </div>
    <div class="computer-vision-section animate fade-in">
      <h2>ADVANCED AI CHATBOT</h2>
      <p>Smart Financial Assistance at Your Fingertips.</p>

      <div class="tracking-features">
        <div class="tracking-feature animate slide-in-left">
          <img src="@/assets/forecast.png" alt="Vehicle Tracking">
          <h3>Instant Financial Insights</h3>
          <p>Ask any question, from budgeting tips to investment advice, and get immediate, data-driven answers.</p>
        </div>
        <div class="tracking-feature animate slide-in-up">
          <img src="@/assets/sales.png" alt="Employee Tracking">
          <h3>Interactive Financial Planning</h3>
          <p>Ask any question, from budgeting tips to investment advice, and get immediate, data-driven answers.</p>
        </div>
        <div class="tracking-feature animate slide-in-right">
          <img src="@/assets/dashboard.png" alt="Advanced Computer Vision">
          <h3>Secure and Confidential</h3>
          <p>Our proprietary system utilizes neural networks to identify the information that matters most. Think of it like the way your brain works, only it never gets tired (or needs 3 cups of coffee to get through the day).</p>
        </div>
      </div>
    </div>
    <div class="partners-section animate fade-in">
      <h2 class="section-title">Integrate with the best tools in the market</h2>
      <p class="section-description">Check out our connected partners. Don’t see your software on the list of partners? <a href="mailto:contact@yourdomain.com">Drop us a note</a> and we’ll get them added.</p>
      <div class="partners">
        <div class="partner animate slide-in-left">
          <img src = "@/assets/shop.png"  alt="Shop-Ware Logo">
          <p>Shop-Ware enables users to take advantage of their lightning-fast workflows to repair more cars every month. <a href="#">Learn more</a></p>
        </div>
        <div class="partner animate slide-in-right">
          <img src="@/assets/tek.png" alt="Tekmetric Logo">
          <p>Tekmetric lets you unleash your shop’s potential with their streamlined workflow settings. <a href="#">Learn more</a></p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TechnologySection',
  data() {
    return {
      features: [
        {
          id: 1,
          title: 'Financial Planning',
          description: 'I help you create and maintain a perfect personal financial plan.',
          icon: "@/assets/tick.png",
        },
        {
          id: 2,
          title: 'Debt and Investment Management',
          description: 'Manage your debts and invest wisely with targeted advice tailored to your goals.',
          icon: "@/assets/tick.png"
        },
        {
          id: 3,
          title: 'Financial Education',
          description: 'Providing knowledge on basic and advanced financial concepts to empower your decisions.',
          icon: "@/assets/tick.png"
        },
        {
          id: 4,
          title: 'Predictive Financial Analytics',
          description: 'Utilize AI to analyze and predict financial trends to make smart decisions.',
          icon: "@/assets/tick.png"
        }
      ]
    };
  },
  methods: {
    learnMore() {
      // Implementation for the Learn More button
    }
  },
  mounted() {
    const observerOptions = {
      threshold: 0.1,
    };

    const observer = new IntersectionObserver((entries, observer) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('animate-visible');
          observer.unobserve(entry.target);
        }
      });
    }, observerOptions);

    const elements = document.querySelectorAll('.animate');
    elements.forEach(el => observer.observe(el));
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&display=swap');

/* Add animations */
.animate {
  opacity: 0;
  transition: opacity 1s ease, transform 1s ease;
}

.animate-visible {
  opacity: 1;
}

.fade-in {
  transform: translateY(20px);
}

.fade-in.animate-visible {
  transform: translateY(0);
}

.slide-in-left {
  transform: translateX(-20px);
}

.slide-in-left.animate-visible {
  transform: translateX(0);
}

.slide-in-right {
  transform: translateX(20px);
}

.slide-in-right.animate-visible {
  transform: translateX(0);
}

.slide-in-up {
  transform: translateY(20px);
}

.slide-in-up.animate-visible {
  transform: translateY(0);
}

/* General Styling */
.features-container {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
  font-family: 'Space Grotesk', sans-serif;
}

.features-title {
  font-size: 24px;
  color: #333;
}

.description {
  margin-bottom: 20px;
}

.feature-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  padding: 20px;
}

.feature {
  padding: 20px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  border-radius: 8px;
  background: #fff;
}

.feature-icon-title {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 10px;
}

.tick-icon {
  width: 20px;
  height: 20px;
  margin-right: 10px;
}

.feature-title {
  font-size: 18px;
  color: #333;
}

.feature-description {
  font-size: 14px;
  color: #666;
}

.insights-section {
  display: flex;
  flex-direction: row-reverse;
  align-items: center;
  justify-content: space-between;
}

.image {
  flex: 1;
  max-width: 50%;
}

.image img {
  width: 100%;
  height: auto;
  display: block;
}

.content {
  flex: 1;
  padding: 20px;
  max-width: 50%;
  background: #f7f7f7; /* light gray background */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* subtle shadow */
}

.list-item {
  display: flex;
  align-items: center;
  margin-bottom: 1em;
}

.list-item img {
  margin-right: 10px;
}

.list-item span {
  font-size: 16px;
  color: #666;
}

button {
  padding: 10px 20px;
  background-color: #007BFF;
  color: white;
  border: none;
  cursor: pointer;
  margin-top: 20px;
  border-radius: 8px;
  font-family: 'Space Grotesk', sans-serif;
}

button:hover {
  background-color: #0056b3; /* darker blue on hover */
}

.computer-vision-section {
  text-align: center;
  margin-top: 40px;
}

.section-title {
  font-size: 24px;
  color: #333;
}

.section-description {
  font-size: 16px;
  color: #666;
  margin-bottom: 20px;
}

.tracking-features {
  display: flex;
  justify-content: space-between; /* This will ensure the items are spread evenly */
  align-items: start; /* Aligns items to the top */
  flex-wrap: nowrap; /* Prevents wrapping into multiple lines */
  margin: 20px 0; /* Adds some vertical spacing */
}

.tracking-feature {
  flex: 1; /* Allows each feature to grow and take up equal space */
  margin: 0 10px; /* Adds horizontal spacing between the features */
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  padding: 20px;
  border-radius: 8px;
  background: #fff; /* Gives a white background to each feature block */
  display: flex; /* Makes the internal content use flexbox for layout */
  flex-direction: column; /* Stacks the content vertically */
}

.tracking-feature img {
  width: 100%; /* Ensures the image takes the full width of the container */
  height: auto; /* Keeps the image aspect ratio */
  margin-bottom: 15px; /* Adds space between the image and the text */
}

.tracking-feature h3 {
  font-size: 18px;
  color: #333;
  margin-bottom: 10px; /* Adds space below the heading */
}

.tracking-feature p {
  font-size: 14px;
  color: #666;
  text-align: left; /* Aligns the text to the left */
}

.partners-section {
  text-align: center;
  padding: 40px 0;
  background-color: #f7f7f7; /* Slightly different background for visual separation */
}

.section-title {
  font-size: 24px;
  color: #333;
}

.section-description {
  font-size: 16px;
  color: #666;
  margin: 20px 0;
}

.partners {
  display: flex;
  justify-content: center;
  gap: 50px; /* Space between partner entries */
}

.partner {
  width: 300px; /* Fixed width for each partner block */
  text-align: left;
}

.partner img {
  width: 100%; /* Makes the logo responsive within the container width */
  height: auto;
  margin-bottom: 10px;
}

.partner p {
  font-size: 14px;
  color: #666;
}
</style>
