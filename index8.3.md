1. HTML Code (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Daily Chronicle | Magazine Layout</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Grid Container -->
    <div class="magazine-container">
        
        <!-- Header Section -->
        <header class="header">
            <h1>The Daily Chronicle</h1>
            <p class="tagline">Your window to the world of design, technology, and culture</p>
        </header>

        <!-- Navigation Section -->
        <nav class="nav">
            <ul>
                <li><a href="#">World</a></li>
                <li><a href="#">Technology</a></li>
                <li><a href="#">Culture</a></li>
                <li><a href="#">Opinion</a></li>
                <li><a href="#">Science</a></li>
            </ul>
        </nav>

        <!-- Main Article Section -->
        <main class="main-article">
            <span class="category">Featured Story</span>
            <h2>The Evolution of Modern Web Layouts: From Floats to Grid Areas</h2>
            <p class="author">By Alex Morgan &bull; October 24, 2026</p>
            <div class="article-content">
                <p class="lead">CSS Grid has fundamentally changed how we design for the web. Gone are the days of hacky floats and rigid frameworks; today's layout engines offer unprecedented structural control.</p>
                <p>With features like named grid areas, developers can sketch visual layouts directly in their stylesheets with intuitive, readable syntax. This mirrors the editorial freedom traditionally reserved for print magazines, allowing asymmetric columns, prominent featured spreads, and flexible sidebars.</p>
                <p>As browsers continue to evolve, the combination of CSS Grid and Subgrid opens up even more sophisticated possibilities, bridging the gap between print-quality typography and dynamic digital interfaces.</p>
            </div>
        </main>

        <!-- Sidebar Section -->
        <aside class="sidebar">
            <div class="widget">
                <h3>Trending News</h3>
                <ul>
                    <li><a href="#">AI Breakthroughs in Architecture</a></li>
                    <li><a href="#">The Rise of Sustainable Urban Design</a></li>
                    <li><a href="#">Minimalism in Digital Interfaces</a></li>
                </ul>
            </div>
            <div class="widget highlight-widget">
                <h3>Editor's Pick</h3>
                <p>Discover how independent creators are reshaping the future of digital publishing.</p>
            </div>
        </aside>

        <!-- Footer Section -->
        <footer class="footer">
            <p>&copy; 2026 The Daily Chronicle. All rights reserved. Designed with CSS Grid Areas.</p>
        </footer>

    </div>

</body>
</html>
2. CSS Code (style.css)
CSS
/* --- Global Styles --- */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Georgia', serif;
    background-color: #f4f4f5;
    color: #27272a;
    line-height: 1.6;
    padding: 20px;
}

/* --- 2. Define a Grid Container --- */
.magazine-container {
    display: grid;
    max-width: 1200px;
    margin: 0 auto;
    gap: 20px;
    
    /* --- 3. Set layout using grid-template-areas --- */
    /* Gives the main article more space (2 fractions) than the sidebar (1 fraction) */
    grid-template-areas:
        "header header"
        "nav nav"
        "main sidebar"
        "footer footer";
    
    grid-template-columns: 2fr 1fr;
    grid-template-rows: auto auto 1fr auto;
}

/* --- 4. Assign a named grid area to each section --- */
.header {
    grid-area: header;
    background-color: #18181b;
    color: #f4f4f5;
    padding: 30px;
    text-align: center;
    border-bottom: 4px solid #f59e0b;
}

.header h1 {
    font-size: 2.8rem;
    font-family: 'Times New Roman', serif;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 5px;
}

.header .tagline {
    font-size: 1rem;
    color: #a1a1aa;
    font-style: italic;
}

.nav {
    grid-area: nav;
    background-color: #ffffff;
    border-top: 1px solid #e4e4e7;
    border-bottom: 1px solid #e4e4e7;
    padding: 10px 20px;
}

.nav ul {
    list-style: none;
    display: flex;
    justify-content: center;
    gap: 30px;
}

.nav a {
    text-decoration: none;
    color: #3f3f46;
    font-family: sans-serif;
    font-weight: 600;
    font-size: 0.95rem;
    text-transform: uppercase;
    transition: color 0.2s ease;
}

.nav a:hover {
    color: #f59e0b;
}

.main-article {
    grid-area: main;
    background-color: #ffffff;
    padding: 40px;
    border: 1px solid #e4e4e7;
}

.main-article .category {
    font-family: sans-serif;
    font-size: 0.8rem;
    font-weight: bold;
    text-transform: uppercase;
    color: #f59e0b;
    letter-spacing: 1px;
}

.main-article h2 {
    font-size: 2.2rem;
    margin: 10px 0 15px 0;
    line-height: 1.2;
}

.main-article .author {
    font-family: sans-serif;
    font-size: 0.85rem;
    color: #71717a;
    margin-bottom: 25px;
    padding-bottom: 15px;
    border-bottom: 1px solid #f4f4f5;
}

.article-content .lead {
    font-size: 1.2rem;
    font-weight: bold;
    margin-bottom: 20px;
    color: #3f3f46;
}

.article-content p {
    margin-bottom: 15px;
}

.sidebar {
    grid-area: sidebar;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.widget {
    background-color: #ffffff;
    padding: 25px;
    border: 1px solid #e4e4e7;
}

.widget h3 {
    font-family: sans-serif;
    font-size: 1.1rem;
    text-transform: uppercase;
    margin-bottom: 15px;
    padding-bottom: 8px;
    border-bottom: 2px solid #18181b;
}

.widget ul {
    list-style: none;
}

.widget ul li {
    margin-bottom: 12px;
}

.widget ul li a {
    text-decoration: none;
    color: #27272a;
    font-family: sans-serif;
    font-size: 0.95rem;
    transition: color 0.2s;
}

.widget ul li a:hover {
    color: #f59e0b;
}

.highlight-widget {
    background-color: #fef3c7;
    border-color: #fde68a;
}

.footer {
    grid-area: footer;
    background-color: #18181b;
    color: #a1a1aa;
    text-align: center;
    padding: 20px;
    font-family: sans-serif;
    font-size: 0.9rem;
}

/* --- Responsive adjustment for smaller screens --- */
@media (max-width: 768px) {
    .magazine-container {
        grid-template-areas:
            "header"
            "nav"
            "main"
            "sidebar"
            "footer";
        grid-template-columns: 1fr;
    }
    
    .nav ul {
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }
}
Assignment Breakdown Checklist:
Header, Navigation, Main Article, Sidebar, and Footer: All sections have been created with distinct semantic HTML tags (<header>, <nav>, <main>, <aside>, <footer>).

Grid Container: Defined via display: grid; on .magazine-container.

grid-template-areas layout: Declared grid tracks and visual map in the CSS ruleset.

Named Grid Areas: Each section is assigned using grid-area: header;, grid-area: nav;, grid-area: main;, grid-area: sidebar;, and grid-area: footer;.

Proportional Spacing: Set via grid-template-columns: 2fr 1fr;, granting the main article twice the horizontal span of the sidebar.

Responsive alignment / Testing: Included a media query block to automatically stack components into a single column on smaller viewports.