# Jekyll Resume + Blog Portfolio Setup

Welcome! This guide will help you set up a personal website with a resume and blog using Jekyll and GitHub Pages. You'll find a list of 20 Jekyll templates below, ready to be customized and deployed. Follow the instructions to set up your portfolio and showcase your resume with personality.

## Getting Started

### **Step 1: Prerequisites**
Before you begin, ensure you have the following installed:
1. **Ruby** (needed for Jekyll)
2. **Jekyll** (static site generator)
   - Install by following this [guide](https://jekyllrb.com/docs/installation/).
   - Note for mac users: Run the commands to configure your shell to automatically use chruby **separately**.
   - If the terminal replies with "you don't have enough permissions," restart the terminal session. This way, the terminal will update. 
3. **GitHub Desktop** (version control)
   - Install from [here](https://desktop.github.com/download/) if not already installed.
4. **GitHub Account**
   - Sign up for free at [GitHub](https://github.com/).

### **Step 2: Choose Your Template**
Here is a list of 20 Jekyll templates that you can use to set up your resume + blog portfolio. Pick one that suits your style and personality!

| Template | Description | Repository Link |
| -------- | ----------- | --------------- |
| **Freelancer Theme** | One-page portfolio with sections for projects and blog. | [Freelancer Theme](https://github.com/jeromelachaud/freelancer-theme) |
| **Resume Template** | Clean, single-page resume with customizable sections. | [Resume Template](https://github.com/jglovier/resume-template) |
| **Lagrange** | Minimalist theme with a professional, portfolio-first design. | [Lagrange](https://github.com/LeNPaul/Lagrange) |
| **Cayman Blog** | Simple blog theme, perfect for easy customization and portfolio. | [Cayman Blog](https://github.com/lorepirri/cayman-blog) |
| **TeXt Theme** | Clean typography, customizable, and responsive for resume + blog. | [TeXt Theme](https://github.com/kitian616/jekyll-TeXt-theme) |
| **Jekyll Clean** | A simple and clean theme with a minimalist approach. | [Jekyll Clean](https://github.com/scotte/jekyll-clean) |
| **DevbyJ Resume** | Resume-focused theme, easily modifiable for blogs. | [DevbyJ Resume](https://github.com/JDevby/jekyll-resume) |
| **Massively** | Bold, visually striking theme, blog-centric. | [Massively](https://github.com/iwiedenm/jekyll-theme-massively) |
| **Jekyll Now** | Instant blogging framework with easy setup, suitable for resumes. | [Jekyll Now](https://github.com/barryclark/jekyll-now) |
| **Hyde** | Elegant minimalist theme for blogs and portfolios. | [Hyde](https://github.com/poole/hyde) |
| **Minimal** | Clean, minimalist layout, perfect for focusing on content. | [Minimal](https://github.com/pages-themes/minimal) |
| **Creative Theme** | One-page creative portfolio with sections for projects and blog. | [Creative Theme](https://github.com/volny/creative-theme-jekyll) |
| **Type** | Modern, lightweight theme ideal for blog + resume portfolios. | [Type](https://github.com/heiswayi/type-theme) |
| **Forty** | Bold, professional portfolio theme for blogs and resumes. | [Forty](https://github.com/andrewbanchich/forty-jekyll-theme) |
| **Dinky** | Super simple and responsive, great for resume portfolios. | [Dinky](https://github.com/broccolini/dinky) |
| **Tale** | Minimalist blog-first theme with easy resume customization. | [Tale](https://github.com/chesterhow/tale) |
| **Prologue** | Personal portfolio theme with a built-in resume section. | [Prologue](https://github.com/chrisbobbe/jekyll-theme-prologue) |
| **Minimal Resume** | Resume-specific theme with easy blog integration. | [Minimal Resume](https://github.com/murraco/jekyll-resume-template) |

You can also download a template from the resources included in our slides. Prioritize templates written in .html format and not .liquid 

### **Step 3: Set Up Your Chosen Template**
1. **Fork the template repository**: 
- Fork the template repository and rename it with (GitHub Username).github.io
- Then clone the repository using GitHub Desktop. Click on code>clone repository> open in GitHub Desktop.
- Lastly choose you will contribut for your own purposes and not to the primary repository. 

2. **Navigate into the folder**:
   ```bash
   cd <repository-folder>
   ```

3. **Install dependencies**:
   If your template uses a `Gemfile`, install dependencies with:
   ```bash
   bundle install
   ```

4. **Serve the site locally**:
   Run the following command to preview your site:
   ```bash
   bundle exec jekyll serve
   ```

5. **Customize Your Content**:
   - Update the `_config.yml` file with your personal information (name, email, social links).
   - Delete the base_url line, and change the url line with your personal (username.github.io) url. 
   - Modify or add Markdown files (`.md`) for your resume and blog content.
   - Use Jekyll’s default folder structure for blog posts (`_posts` folder).

6. **Deploy to GitHub Pages**:
   Push your changes to GitHub Desktop to make your site live:

   Then, enable GitHub Pages under your repository settings to deploy your site at `https://username.github.io`.

### **Step 4: Personalize Your Resume + Blog**
**Each template provides different customization options, allowing you to add a personal touch to your online portfolio. Make sure to:**
- Go to my [workshop repository](https://github.com/leonardocuellargold/website_workshop/blob/master/resume.html). And feel free to copy the **resume.html** template. 
- Update your resume with your work experience, education, and skills.
- Add blog posts to share your thoughts, projects, or interests.

### **Step 5: Add a Collection for Projects**

To showcase your projects alongside your resume, follow these steps to add a collection named `projects`:

1. **Define the Collection in `_config.yml`:**
Open your `_config.yml` file and add the following lines to define a collection named `projects`:
    
    ```yaml
    collections:
      projects:
        output: true
        permalink: /projects/:path/
    
    ```
    
    This configuration enables the collection and specifies the URL structure for your project pages.
    
2. **Create the Collection Directory:**
In your Jekyll site’s root directory, create a new folder named `_projects`. This is where you’ll store each project as a Markdown file.
3. **Create a Layout for Projects:**
To define how each project page should look, create a file named `project.html` inside the `_layouts` folder. This file will serve as the layout for your project pages.
    
    ```html
    <!-- _layouts/project.html -->
    ---
    layout: default
    ---
    
    <article class="project-page">
      <h1>{{ page.title }}</h1>
      <p class="project-description">{{ page.description }}</p>
    
      {% if page.images %}
        <div class="project-images">
          {% for image in page.images %}
            <img src="{{ image }}" alt="{{ page.title }} image {{ forloop.index }}" loading="lazy">
          {% endfor %}
        </div>
      {% endif %}
    
      <div class="project-content">
        {{ content }}
      </div>
    
      {% if page.repo_url %}
        <a href="{{ page.repo_url }}" class="repo-link" target="_blank">View on GitHub</a>
      {% endif %}
    </article>
    
    ```
    
    This layout defines how the project pages will be structured, with a title, description, optional images, and a GitHub link if available.
    
4. **Add Project Posts:**
Inside the `_projects` directory, create Markdown files for each project. For example, create a file named `project1.md` with the following content:
    
    ```yaml
    ---
    layout: project
    title: "Project 1: My Awesome Project"
    description: "A brief description of what this project is about."
    repo_url: "<https://github.com/username/project1-repo>"
    images:
      - "<https://example.com/images/project1-1.jpg>"
      - "<https://example.com/images/project1-2.jpg>"
    ---
    
    Here, you can add more detailed information about the project, such as features, technologies used, or key achievements.
    
    ```
    
5. **Create an Index Page for Projects:**
To list your projects, create a file named `projects.html` (or `index.html` inside the `_projects` folder if you prefer) with the following content:
    
    ```html
    <!-- projects.html -->
    ---
    layout: default
    title: "My Projects"
    permalink: /projects/
    ---
    
    <section class="projects-section">
      <h1>{{ page.title }}</h1>
      <p class="description">Explore my collection of projects, where I showcase my work and creativity.</p>
    
      <div class="projects-grid">
        {% for project in site.projects %}
          <div class="project-card">
            <div class="project-card-header">
              {% if project.images %}
                <img src="{{ project.images[0] }}" alt="{{ project.title }} cover image" class="project-cover" loading="lazy">
              {% endif %}
            </div>
            <div class="project-card-body">
              <h2 class="project-title">{{ project.title }}</h2>
              <p class="project-description">{{ project.description }}</p>
              <a href="{{ project.url }}" class="project-link">View Details</a>
            </div>
          </div>
        {% endfor %}
      </div>
    </section>
    
    ```
    
    This HTML code creates a visually appealing index page listing all your projects. You can customize the classes and styling to fit your theme.
    
6. **Update Your Navigation (Optional):**
If you want your homepage or other pages to include a link to the projects page, add a navigation link in your `_data/navigation.yml` (or directly in your HTML if using manual navigation).
    
    ```yaml
    - title: "Projects"
      url: "/projects/"
    
    ```
    
    Or, if manually adding HTML links:
    
    ```html
    <nav>
      <ul>
        <li><a href="/projects/">Projects</a></li>
        <li><a href="/blog/">Blog</a></li>
        <!-- Add more links as needed -->
      </ul>
    </nav>
    
    ```
    
### **Additional Resources**
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

---

Feel free to explore, experiment, and build something unique! If you run into any issues, don't hesitate to ask for help.

Good luck!
