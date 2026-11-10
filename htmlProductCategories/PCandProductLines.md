<img width="1221" height="550" alt="image" src="https://github.com/user-attachments/assets/1ac00cf1-271a-47b7-bfb3-ab5ea95f96b7" />


```text
# Project: Interactive Product Category & Product Catalogue for Google Sites

## 1. Objective

Create a responsive, interactive product catalogue using **HTML5, CSS3 and JavaScript** that can be embedded into Google Sites.

The design and layout should closely follow the attached reference image.

The catalogue should display:
- Multiple main product categories.
- Multiple product lines under each category.
- Product images under each product line.
- JSON-based product descriptions for every product line
- Previous and Next navigation to browse products within a selected product line.

The application should be easy to maintain, with new categories, product lines, images and descriptions added simply by updating folders and JSON files.

## 2. Overall Layout

Follow the attached reference image for the overall screen structure.

Divide the interface into three main sections:

### A. Top Header
- Full-width horizontal header.
- Company logo on the left.
- Company tagline displayed alongside or below the logo.
- Fixed header height.
- Clean, minimal and professional appearance.

### B. Left Sidebar – Product Navigation
- Vertical sidebar positioned below the header.
- Approximately 200px wide on desktop.
- Display all main product categories.
- Main product categories should be expandable/collapsible.
- Clicking a category should reveal all associated product lines.
- Clicking a product line should load its product gallery in the right-hand display frame.
- Highlight the currently selected product category and product line.
- Use expandable arrow icons (+/-) for categories.

Example:

**Guest Amenities & Hospitality Consumables**
- Toiletry & Grooming Kits
- Dental & Shaving Kits
- Sewing Kits
- Shoe Polish Kits
- Disposable Slippers
- Hotel Water Bottles
- Welcome Gift Boxes
- Guest Stationery
- Branded Packaging
- Eco-Friendly Amenity Kits

Additional product categories should be supported without changing the application code.

### C. Right Frame – Product Display Area

This should occupy the remaining available screen width.

When a user clicks a product line in the left sidebar, display the following:

**1. Product Image**
- Display the product image prominently.
- Maintain original image proportions.
- Use contain/fit styling without image distortion.
- Centre the image within the display frame.

**2. Product Description**
Read product information from the JSON file associated with the selected product line.

Display relevant fields such as:
- Product Name
- Product Description
- Material / Composition
- Available Sizes
- Available Colours
- Customisation / Branding Options
- Packaging Details
- Quality Standards
- Warranty (where applicable)

**3. Image Navigation**
Provide:
- Previous link/button.
- Next link/button.
- Current image number and total images (e.g. 2 of 8).

Navigation should browse only images belonging to the currently selected product line.

When the last image is reached, the Next button should return to the first image. Similarly, Previous from the first image should display the last image.

## 3. Category and Product Line Behaviour

Implement the following interaction:

1. Load the application with the company header and product category sidebar.
2. All main product categories should initially appear collapsed.
3. Clicking a main category expands its product lines.
4. Clicking another category should allow the previous category to collapse.
5. Clicking a product line loads its associated images and JSON description in the right frame.
6. The selected product line should remain highlighted.
7. Previous and Next should navigate all images under that product line.
8. Switching to another product line should load its own images and JSON description.

## 4. Automatic Folder-Based Catalogue Structure

Use a folder-based architecture so that products can be added without manually modifying HTML or JavaScript.

Suggested folder structure:

```text
ProductCatalogue/
│
├── index.html
├── css/
│   └── style.css
│
├── js/
│   ├── app.js
│   ├── navigation.js
│   └── product-loader.js
│
├── data/
│   └── categories.json
│
├── assets/
│   ├── logo.png
│   └── default-product.png
│
└── products/
    │
    ├── Guest-Amenities/
    │   │
    │   ├── category.json
    │   │
    │   ├── Toiletry-Grooming-Kits/
    │   │   ├── product.json
    │   │   ├── image1.jpg
    │   │   ├── image2.jpg
    │   │   └── image3.jpg
    │   │
    │   ├── Dental-Shaving-Kits/
    │   │   ├── product.json
    │   │   ├── image1.jpg
    │   │   └── image2.jpg
    │   │
    │   └── Sewing-Kits/
    │       ├── product.json
    │       ├── image1.jpg
    │       └── image2.jpg
    │
    ├── Bed-Bath-Linen/
    │   ├── category.json
    │   ├── Bedsheets/
    │   │   ├── product.json
    │   │   ├── image1.jpg
    │   │   └── image2.jpg
    │   └── Towels/
    │       ├── product.json
    │       ├── image1.jpg
    │       └── image2.jpg
    │
    └── Tableware-Crockery/
        ├── category.json
        ├── Crockery/
        │   ├── product.json
        │   ├── image1.jpg
        │   └── image2.jpg
        └── Buffet-Servables/
            ├── product.json
            ├── image1.jpg
            └── image2.jpg
```

## 5. JSON Configuration

### A. categories.json

This file should control all main product categories and their product lines.

Example:

```json
{
  "categories": [
    {
      "id": "guest-amenities",
      "name": "Guest Amenities & Hospitality Consumables",
      "folder": "Guest-Amenities",
      "productLines": [
        {
          "id": "toiletry-kits",
          "name": "Toiletry & Grooming Kits",
          "folder": "Toiletry-Grooming-Kits"
        },
        {
          "id": "dental-kits",
          "name": "Dental & Shaving Kits",
          "folder": "Dental-Shaving-Kits"
        }
      ]
    }
  ]
}
```

### B. product.json

Each product line must have its own JSON file.

Example:

```json
{
  "productLine": "Toiletry & Grooming Kits",
  "description": "Complete guest toiletry and grooming solutions for hotels and hospitality businesses.",
  "products": [
    {
      "name": "Premium Toiletry Kit",
      "image": "image1.jpg",
      "description": "Premium guest toiletry kit for hotel use.",
      "material": "Customised packaging",
      "sizes": "Multiple options",
      "customisation": "Hotel logo branding available",
      "packaging": "Individual packaging",
      "quality": "Custom quality specifications"
    },
    {
      "name": "Eco-Friendly Toiletry Kit",
      "image": "image2.jpg",
      "description": "Eco-conscious guest amenity kit.",
      "material": "Eco-friendly materials",
      "sizes": "Multiple options",
      "customisation": "Custom branding available",
      "packaging": "Individual packaging",
      "quality": "Custom quality specifications"
    }
  ]
}
```

## 6. Design and Styling Requirements

- Follow the attached reference image's overall layout.
- Grey header with white company logo and tagline.
- Black or dark background for the main content area.
- Left sidebar with a clearly defined boundary.
- Use a subtle pink accent border/highlight similar to the reference image.
- Use white or light-coloured typography.
- Modern, premium and minimalist visual appearance.
- Smooth category expansion and collapse animations.
- Responsive layout for desktop, tablet and mobile.
- Keep the product image and description neatly organised within the right frame.

## 7. Technical Requirements

- HTML5, CSS3 and Vanilla JavaScript.
- No dependency on external JavaScript frameworks.
- Separate HTML, CSS, JavaScript and JSON files.
- Dynamic category and product-line loading.
- JSON-driven product descriptions.
- Support multiple images per product line.
- Avoid hardcoding product categories or image filenames in JavaScript.
- Include error handling for missing images or JSON files.
- Include a default placeholder image when an image is unavailable.
- Optimise image loading and navigation.
- Ensure compatibility with Google Sites embedding.

**Important Google Sites consideration:** Browsers cannot automatically scan arbitrary local folders. Implement the catalogue using JSON manifests and relative image paths, with the application and assets hosted at an accessible HTTPS location. Google Sites should embed the hosted application using its Embed URL option or an HTML embed where supported.

## 8. Deliverables

Generate a complete working project containing:

1. index.html
2. style.css
3. app.js
4. navigation.js
5. product-loader.js
6. categories.json
7. Sample product.json files.
8. Sample product images or image placeholders.
9. Complete folder structure.
10. Instructions for adding new product categories, product lines, images and descriptions.
11. Instructions for hosting and embedding the application in Google Sites.

## 9. Final Expected Behaviour

The final application should behave like an interactive digital product catalogue.

- Left side: Expandable product category and product-line navigation.
- Right side: Product image and JSON-driven product description.
- Bottom or side of product display: Previous and Next navigation.
- Top: Company logo and tagline.

A user should be able to browse multiple categories, select a product line and navigate through all its products without refreshing the entire page.

Build the application with scalability in mind so hundreds of product lines and multiple images per product line can be supported without redesigning the application.

First generate the complete working project with sample data. Do not provide isolated code snippets. Ensure all files work together.




```
