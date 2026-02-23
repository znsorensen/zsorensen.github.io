# znsorensen.github.io
Website Draft

========================================
FILE: _config.yml
========================================
title: "Your Name"
description: "Consulting, writing, and selected work."
url: "znsorensen.github.io" # Change if using custom domain
markdown: kramdown
permalink: /blog/:year/:month/:day/:title/


========================================
FILE: assets/style.css
========================================
:root { color-scheme: light dark; }

body {
  max-width: 760px;
  margin: 40px auto;
  padding: 0 16px;
  font: 16px/1.6 system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
}

header, footer {
  margin: 24px 0;
}

nav a {
  margin-right: 14px;
  text-decoration: none;
}

nav a:hover {
  text-decoration: underline;
}

h1, h2 {
  line-height: 1.2;
}

.post-meta {
  opacity: 0.7;
  font-size: 0.95em;
}

hr {
  opacity: 0.3;
}


========================================
FILE: _layouts/default.html
========================================
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>{{ page.title }} | {{ site.title }}</title>
  <meta name="description" content="{{ site.description }}" />
  <link rel="stylesheet" href="/assets/style.css" />
</head>
<body>

<header>
  <h1>
    <a href="/" style="text-decoration:none;color:inherit;">
      {{ site.title }}
    </a>
  </h1>
  <p>{{ site.description }}</p>

  <nav>
    <a href="/">Home</a>
    <a href="/blog/">Blog</a>
    <a href="/resume/">Resume</a>
    <a href="/calendar/">Calendar</a>
  </nav>
  <hr />
</header>

<main>
  {{ content }}
</main>

<footer>
  <hr />
  <p>© {{ "now" | date: "%Y" }} {{ site.title }}</p>
</footer>

</body>
</html>


========================================
FILE: _layouts/post.html
========================================
---
layout: default
---
<article>
  <h2>{{ page.title }}</h2>
  <p class="post-meta">
    {{ page.date | date: "%B %d, %Y" }}
  </p>
  {{ content }}
</article>


========================================
FILE: index.md
========================================
---
layout: default
title: Home
---

Hi — I’m **Your Name**.

I do consulting/freelance work in **[your area]** and write about **[topics]**.

## Current Focus
- Project or client work
- Research or interests
- Availability status

## Contact
- Email: you@yourdomain.com
- LinkedIn: https://linkedin.com/in/yourprofile
- GitHub: https://github.com/yourusername


========================================
FILE: blog.md
========================================
---
layout: default
title: Blog
permalink: /blog/
---

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}


========================================
FILE: _posts/2026-02-23-welcome.md
========================================
---
layout: post
title: "Welcome"
date: 2026-02-23
---

This is my first post.

I’ll use this space for notes, case studies, ideas, and longer reflections.


========================================
FILE: resume.md
========================================
---
layout: default
title: Resume
permalink: /resume/
---

# Your Name
Consultant / Freelancer — City, State  
Email: you@yourdomain.com  

---

## Services
- Strategy / Advisory
- Project consulting
- Workshops / Speaking

---

## Experience

### Role / Client — Dates
- Key achievement or measurable outcome
- Another impact-driven bullet

### Previous Role — Dates
- Key contribution
- Results achieved

---

## Education
Institution — Degree — Year


========================================
FILE: calendar.md
========================================
---
layout: default
title: Calendar
permalink: /calendar/
---

Below is my public events calendar.

<iframe
  src="https://calendar.google.com/calendar/embed?src=YOUR_CALENDAR_ID&ctz=America%2FNew_York"
  style="border:0"
  width="100%"
  height="600"
  frameborder="0"
  scrolling="no">
</iframe>

To embed your calendar:

1. Open Google Calendar
2. Settings → Select calendar
3. Enable “Make available to public”
4. Copy the Embed Code
5. Replace YOUR_CALENDAR_ID above
