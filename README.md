Here’s a **README.md** file for your project with a step-by-step explanation and details of the code:

---

## House Rental Webpage

This project is a webpage for a fictional house rental service. It showcases property listings, a search feature, a favorite system, and a responsive image carousel.

### Table of Contents
1. [Project Structure](#project-structure)
2. [Setup Instructions](#setup-instructions)
3. [File Explanations](#file-explanations)
4. [Code Walkthrough](#code-walkthrough)
   - [HTML](#html)
   - [CSS](#css)
   - [JavaScript](#javascript)

---

### Project Structure

Your project files are organized as follows:

```plaintext
HouseRental/
│
├── index.html         # Main HTML file for the webpage
├── styles.css         # External CSS file for styling
├── images/            # Directory containing images for carousel and property listings
│   ├── logo.jpg       # Logo image displayed in the navigation bar
│   ├── slider1.jpg    # Carousel image 1
│   ├── slider2.jpg    # Carousel image 2
│   ├── ...            # Additional images for carousel and properties
```

### Setup Instructions

1. **Unzip the `images.zip` file** and place the `images` folder in the same directory as `index.html`.
2. **Open `index.html`** in a web browser to view the webpage.

### File Explanations

- **index.html**: Contains the structure of the webpage, including navigation, carousel, property listings, and footer.
- **styles.css**: Contains CSS styles for layout, colors, and animations.
- **images/**: Folder holding all images used on the website (logo, carousel images, and property images).

### Code Walkthrough

#### HTML

The HTML file `index.html` provides the webpage structure. Key sections include:

1. **Head Section**:
   ```html
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>House Rental</title>
       <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
       <link rel="stylesheet" href="styles.css">
   </head>
   ```
   - The Bootstrap CSS is loaded for responsive design.
   - `styles.css` is linked for custom styling.

2. **Navigation Bar**:
   ```html
   <nav class="navbar navbar-expand-lg navbar-light bg-cream">
       <img src="images/logo.jpg" alt="Logo" class="logo">House Rentals
       <div class="collapse navbar-collapse" id="navbarNav">
           <ul class="navbar-nav mx-auto">
               <li class="nav-item">
                   <input type="text" id="search-bar" class="form-control" placeholder="What are you looking for?" onkeyup="searchProperties()" style="width: 300px;">
               </li>
           </ul>
       </div>
   </nav>
   ```
   - Displays the `logo.jpg` image next to the "House Rentals" title.
   - A search bar allows users to filter property listings in real-time.

3. **Carousel Section**:
   ```html
   <div id="threeImageSlider" class="carousel slide" data-ride="carousel">
       <div class="carousel-inner">
           <!-- Each carousel item displays three images in a row -->
           <div class="carousel-item active">
               <div class="row">
                   <div class="col"><img src="images/slider1.jpg" class="d-block w-100" alt="Slider Image 1" style="height: 200px; object-fit: cover;"></div>
                   <!-- Additional images follow similarly -->
               </div>
           </div>
       </div>
       <!-- Navigation controls for carousel -->
       <a class="carousel-control-prev" href="#threeImageSlider" role="button" data-slide="prev">
           <span class="carousel-control-prev-icon" aria-hidden="true"></span>
       </a>
   </div>
   ```
   - Contains the carousel showing three images at a time.
   - Navigation controls allow users to cycle through images.

4. **Property Listings**:
   ```html
   <div class="container mt-4">
       <h2>Featured Properties</h2>
       <div class="row" id="property-listings">
           <div class="col-md-4 property-card" data-name="Luxury Villa">
               <div class="card">
                   <img src="images/property1.jpg" class="card-img-top" alt="Property 1">
                   <div class="card-body">
                       <h5 class="card-title">Luxury Villa</h5>
                       <p class="card-text">Location: Los Angeles, CA</p>
                       <label class="favorite-label">
                           <input type="checkbox" onchange="toggleFavorite(this, 'Luxury Villa')"> Add to Favorites
                       </label>
                   </div>
               </div>
           </div>
       </div>
   </div>
   ```
   - Contains individual property cards with information, images, and a "Add to Favorites" checkbox.

#### CSS (styles.css)

The CSS file contains styling for the website layout and theme. Key parts include:

1. **Body and Navbar Styling**:
   ```css
   body {
       background-color: #FFFDD0; /* Cream background color */
       font-family: Arial, sans-serif; /* Font family for text */
   }
   nav {
       background-color: #F5F5DC; /* Cream color for navbar */
       padding: 10px; /* Padding around navbar */
   }
   ```
   - Sets a cream background for the body.
   - Navbar has a lighter cream color for contrast.

2. **Property Card Styling**:
   ```css
   .property-card {
       margin-bottom: 20px;
       box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Adds shadow */
       border-radius: 10px; /* Rounded corners */
       overflow: hidden; /* Apply rounded corners to content */
       transition: transform 0.2s; /* Smooth scaling on hover */
   }
   .property-card:hover {
       transform: scale(1.02); /* Slightly enlarges on hover */
   }
   ```
   - Styles individual property cards with shadows, rounded corners, and a hover effect.

3. **Carousel Styling**:
   ```css
   .carousel-inner img {
       max-width: 100%; /* Ensures images are responsive */
       height: auto; /* Maintains aspect ratio */
   }
   ```
   - Ensures carousel images are responsive and correctly sized.

4. **Logo Styling**:
   ```css
   .logo {
       height: 30px; /* Sets the logo's height */
       vertical-align: middle; /* Aligns with text */
       margin-right: 8px; /* Space between logo and title */
   }
   ```

#### JavaScript (index.html)

The JavaScript functions handle user interactions:

1. **`toggleFavorite` Function**:
   ```javascript
   function toggleFavorite(checkbox, propertyName) {
       if (checkbox.checked) {
           alert(propertyName + ' has been added to your favorites!');
       } else {
           alert(propertyName + ' has been removed from your favorites!');
       }
   }
   ```
   - Adds/removes a property from favorites with an alert to the user.

2. **`searchProperties` Function**:
   ```javascript
   function searchProperties() {
       let input = document.getElementById('search-bar').value.toLowerCase();
       let propertyCards = document.querySelectorAll('.property-card');
       propertyCards.forEach(card => {
           let propertyName = card.getAttribute('data-name').toLowerCase();
           card.style.display = propertyName.includes(input) ? 'block' : 'none';
       });
   }
   ```
   - Filters properties based on the search input, showing only those that match.

### Final Notes

Open `index.html` in a web browser to explore the functionality, view properties, and test adding favorites or searching properties. This setup provides a responsive and interactive layout for a house rental website.
