# BLACK&RHOOD E-Commerce Website: Development Plan

A stage-by-stage plan to build the **BLACK&RHOOD** website, structured in phases where each phase delivers a tangible, working part of the website. This plan is based on the official PRD and design mockups.

---

## **Phase 0: Foundation and Setup**

This initial phase is about preparing your tools and environment. It's the groundwork that ensures the rest of the project is built on a solid foundation.

### **1. Version Control Setup**

Initialize a Git repository for your project. This is non-negotiable for tracking changes and managing your code professionally.

### **2. Project Structure**

Create a clean folder structure:

```
index.html (for the homepage)
/pages/ (for other HTML files like about.html, shop.html, etc.)
/css/ (for your stylesheet, e.g., style.css)
/js/ (for your JavaScript file, e.g., main.js)
/assets/ or /images/ (for the logo, product images, and lifestyle visuals)
```

### **3. Supabase Backend Setup**

* Create a new project on Supabase.
* Navigate to the Table Editor and create the two tables specified in the PRD:

  * **products** table with fields: `id`, `name`, `description`, `price`, `colors`, `sizes`, `image_url`, `in_stock`.
  * **orders** table with fields: `id`, `customer_name`, `product_id`, `size`, `color`, `phone`, `address`, `status`.
* Keep your **Project URL** and **anon public key** handy. You'll need them to connect your website to the database.

---

## **Phase 1: The Static Skeleton**

The goal of this phase is to build a visible, navigable, but static version of the website. At the end of this phase, you'll have a site that looks complete but doesn't yet load data from the backend.

### **1. Global Styles & Reusable Components**

* In your `style.css`, define the core brand identity: theme, colors, and typography as outlined in the PRD.
* Focus on creating a mobile-first layout.
* Build the **Header** and **Footer** as reusable components.

  * The header should contain the logo and navigation links (HOME, SHOP, ABOUT).
  * The footer should have social media and contact links.

### **2. Build the Static Pages**

* **Homepage (`index.html`)**: Create the hero section with the headline *"Wear the Story. Own the Rhood..."* and the "Shop Now" / "Learn More" buttons. For the "Featured Products" section, use hardcoded placeholder content based on the mockups.
* **About Us Page (`about.html`)**: Add the brand story, mission, and values directly from the PRD and mockups.
* **Size Guide Page (`sizeguide.html`)**: Build the HTML table with the sizing information provided in the documents.

✅ **Deliverable for Phase 1:** A multi-page static website. You can click between the Home, About, and Size Guide pages. The design is in place, but product data is just placeholder text and images.

---

## **Phase 2: Dynamic Content Integration**

This is a major milestone where the website comes to life. You'll connect the frontend to your Supabase backend to display dynamic product information.

### **1. Connect to Supabase**

In your `main.js` file, use the Supabase client library to establish a connection using the API keys from Phase 0.

### **2. Populate Supabase with Data**

Manually add a few sample products to your `products` table in the Supabase dashboard. Use the information from the mockups, such as **"Black&Rhood Classic Tee"** for ₦8,500. Upload placeholder images and add their URLs to the `image_url` field.

### **3. Fetch and Display Products**

* Create an async JavaScript function to fetch all records from your `products` table.
* On the **Shop Page (`shop.html`)**, use JavaScript to dynamically generate the HTML for each product card (image, name, price, etc.) based on the data you fetched.
* Update the Homepage to call the same function but limit it to 3–4 items for the "Featured Products" section.

✅ **Deliverable for Phase 2:** A dynamic Shop page and Homepage. The product grids are no longer hardcoded; they display real data directly from your Supabase database.

---

## **Phase 3: Interactivity and Final Pages**

Now you'll add the core user interactions and build the remaining informational pages.

### **1. Implement "Order via WhatsApp"**

For each product card, ensure the **ORDER VIA WHATSAPP** button is an `<a>` tag.

* The `href` attribute should point to the brand's WhatsApp link: `https://wa.me/2348105319`.
* Use JavaScript to dynamically construct a pre-filled message in the URL, like:

  ```
  ?text=I'd%20like%20to%20order%20the%20[Product%20Name]
  ```

  to improve the user experience.

### **2. Add Mobile Navigation**

Implement the JavaScript for the hamburger navigation menu for mobile screens. The script should toggle a class on your navigation element to show or hide it.

### **3. Build Final Informational Pages**

* **Payments & Orders Page (`payments.html`)**: Add the bank transfer details and the step-by-step ordering instructions.
* **Shipping & Delivery Page (`shipping.html`)**: Include the information about nationwide delivery, time, and fees.

✅ **Deliverable for Phase 3:** A functionally complete website. Users can browse dynamic products, initiate an order on WhatsApp, and view all payment and shipping information. Mobile navigation works correctly.

---

## **Phase 4: Responsive Styling and Final Testing**

With all functionality in place, the final phase is about polishing the user experience across all devices and ensuring everything is bug-free.

### **1. Implement Responsive CSS**

* Go through each page and fine-tune the CSS for different screen sizes using CSS media queries.
* Transition from the single-column mobile layouts to the multi-column desktop layouts seen in the mockups.
* Pay close attention to font scaling, button sizes, and image dimensions.

### **2. Comprehensive Testing**

Use your browser's developer tools to emulate various mobile devices.
Test all functionality:

* Do all navigation links work?
* Does product data load correctly from Supabase?
* Does the WhatsApp integration work and pre-fill the message correctly?
* Is the layout free of visual bugs on all screen sizes?

✅ **Deliverable for Phase 4:** A polished, fully responsive, and thoroughly tested website that provides a seamless experience on any device.

---

## **Phase 5: Deployment**

The final step is to make the website live for the world to see.

### **1. Choose a Hosting Provider**

For a static site with a JS backend connection, platforms like **Netlify**, **Vercel**, or **GitHub Pages** are excellent choices.

### **2. Deploy**

Connect your Git repository to your chosen host and deploy the site.
