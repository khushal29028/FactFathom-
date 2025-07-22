<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>FactFathom News</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', sans-serif;
    }

    body {
      background-color: #f4fefb;
      color: #2c3e50;
    }

    header {
      background: linear-gradient(to right, #1abc9c, #16a085);
      color: #ffffff;
      padding: 1.5rem 2rem;
      text-align: center;
    }

    .header-content {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .header-content img {
      height: 50px;
      width: auto;
      border-radius: 8px;
    }

    header h1 {
      font-size: 2.8rem;
      letter-spacing: 1px;
    }

    nav ul {
      list-style: none;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 1rem;
    }

    nav ul li {
      background: #ffffffaa;
      padding: 0.6rem 1.2rem;
      border-radius: 8px;
      cursor: pointer;
      color: #145a32;
      font-weight: bold;
      transition: background 0.3s, transform 0.3s;
    }

    nav ul li:hover {
      background: #d1f2eb;
      transform: scale(1.05);
    }

    .hero {
      background: linear-gradient(to right, #dfffe9, #e0fffa);
      color: #145a32;
      padding: 2rem;
      text-align: center;
    }

    .hero h2 {
      font-size: 2.2rem;
      margin-bottom: 0.6rem;
    }

    .news-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 1.5rem;
      padding: 2rem;
    }

    .news-grid article {
      background: #ffffff;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
      transition: transform 0.3s, box-shadow 0.3s;
    }

    .news-grid article:hover {
      transform: translateY(-8px);
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
    }

    .news-grid img {
      width: 100%;
      height: auto;
    }

    .news-grid h3, .news-grid p {
      padding: 0.8rem;
      color: #2c3e50;
    }

    .comments-section, .rating-section {
      background: #ecfdf5;
      padding: 2rem;
      margin: 2rem;
      border-radius: 12px;
    }

    .comments-section h2, .rating-section h2 {
      margin-bottom: 1rem;
      color: #117a65;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }

    form input, form textarea {
      padding: 0.7rem;
      border: 1px solid #c8e6c9;
      border-radius: 8px;
      background: #ffffff;
      color: #2c3e50;
    }

    form button {
      padding: 0.8rem;
      background: #1abc9c;
      border: none;
      border-radius: 8px;
      color: white;
      font-weight: bold;
      cursor: pointer;
      transition: background 0.3s;
    }

    form button:hover {
      background: #16a085;
    }

    .comment {
      background: #ffffff;
      margin-top: 1rem;
      padding: 0.6rem;
      border-left: 4px solid #1abc9c;
      border-radius: 6px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.06);
    }

    .stars span {
      font-size: 2rem;
      cursor: pointer;
      color: #1abc9c;
      transition: transform 0.2s;
    }

    .stars span:hover {
      transform: scale(1.2);
    }

    #ratingValue {
      margin-top: 0.5rem;
      font-style: italic;
      color: #117a65;
    }

    footer {
      background: #145a32;
      color: #ffffff;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }

    footer a {
      color: #b2f5ea;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <header>
    <div class="header-content">
      <img src="logo.png" alt="FactFathom Logo" />
      <h1>FactFathom</h1>
    </div>
    <nav>
      <ul>
        <li>Home</li>
        <li>World</li>
        <li>Politics</li>
        <li>Business</li>
        <li>Science</li>
        <li>Sports</li>
      </ul>
    </nav>
  </header>

  <section class="hero">
    <div class="hero-text">
      <h2>Top Story Headline Goes Here</h2>
      <p>Catch the latest global updates with deep insights.</p>
    </div>
  </section>

  <section class="news-grid">
    <article>
      <img src="https://via.placeholder.com/400x200" alt="News" />
      <h3>Headline 1</h3>
      <p>Brief description of the news article to draw readers in.</p>
    </article>
    <article>
      <img src="https://via.placeholder.com/400x200" alt="News" />
      <h3>Headline 2</h3>
      <p>Another news summary with engaging visual and title.</p>
    </article>
    <article>
      <img src="https://via.placeholder.com/400x200" alt="News" />
      <h3>Headline 3</h3>
      <p>This story reveals something important and timely.</p>
    </article>
    <article>
      <img src="https://via.placeholder.com/400x200" alt="News" />
      <h3>Headline 4</h3>
      <p>Short highlight about events, interviews or updates.</p>
    </article>
  </section>

  <section class="comments-section">
    <h2>Comments</h2>
    <form id="commentForm">
      <input type="text" id="name" placeholder="Your name" required />
      <textarea id="comment" placeholder="Your comment" required></textarea>
      <button type="submit">Post Comment</button>
    </form>
    <div id="commentList"></div>
  </section>

  <section class="rating-section">
    <h2>Rate This Website</h2>
    <div class="stars">
      <span onclick="rate(1)">★</span>
      <span onclick="rate(2)">★</span>
      <span onclick="rate(3)">★</span>
      <span onclick="rate(4)">★</span>
      <span onclick="rate(5)">★</span>
    </div>
    <p id="ratingValue"></p>
  </section>

  <footer>
    <p>© 2025 FactFathom News | All rights reserved.</p>
    <p>Contact: <a href="mailto:info@factfathom.com">info@factfathom.com</a></p>
  </footer>

  <script>
    const form = document.getElementById("commentForm");
    const commentList = document.getElementById("commentList");

    form.addEventListener("submit", function (e) {
      e.preventDefault();
      const name = document.getElementById("name").value;
      const comment = document.getElementById("comment").value;

      const div = document.createElement("div");
      div.className = "comment";
      div.innerHTML = `<strong>${name}</strong><p>${comment}</p>`;
      commentList.prepend(div);

      form.reset();
    });

    function rate(star) {
      document.getElementById("ratingValue").textContent = `You rated this ${star} star${star > 1 ? 's' : ''}.`;
    }
  </script>
</body>
</html>
