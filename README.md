<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Кавомашина Rainberg – Знижка та Замовлення</title>
  <style>
    /* Reset and base styles */
    *,
    *::before,
    *::after {
      box-sizing: border-box;
    }

    /* Повернуто шрифт на 'Montserrat' */
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap');

    body {
      font-family: 'Montserrat', sans-serif; /* Повернуто попередній шрифт */
      background: linear-gradient(135deg, #6dd5fa, #2980b9); /* Повернуто попередній фон */
      margin: 0;
      padding: 20px;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      flex-direction: column;
    }

    .container {
      background: white;
      border-radius: 18px;
      /* Enhanced shadow for more depth */
      box-shadow: 0 25px 50px rgba(0,0,0,0.35);
      max-width: 480px;
      width: 100%;
      padding: 35px 30px 45px;
      box-sizing: border-box;
      text-align: center;
      position: relative;
      margin: 40px auto 20px;
      user-select: none;
      min-width: 0;
      word-wrap: break-word;
      overflow-wrap: break-word;
    }

    h1 {
      margin-bottom: 15px;
      /* Градієнтний текст для основного заголовка (повернуто попередні кольори) */
      background: linear-gradient(45deg, #0a3d62, #3498db);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      color: transparent; /* Fallback for browsers that don't support text gradients */
      font-weight: 700;
      font-size: 30px;
      letter-spacing: 0.05em;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.1); /* Subtle text shadow */
    }

    /* Gallery */
    .gallery {
      position: relative;
      max-width: 400px;
      margin: 0 auto;
      border-radius: 15px;
      overflow: hidden;
      /* Тінь галереї (повернуто попередні кольори) */
      box-shadow: 0 10px 30px rgba(41, 128, 185, 0.5);
    }

    .gallery img {
      width: 100%;
      display: none;
      transition: transform 0.3s ease;
      border-radius: 15px;
    }

    .gallery img.active {
      display: block;
    }

    .gallery img:hover {
      transform: scale(1.05);
    }

    .gallery button {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(0,0,0,0.3);
      border: none;
      color: white;
      font-size: 28px;
      padding: 10px 15px;
      border-radius: 50%;
      cursor: pointer;
      user-select: none;
      transition: background 0.3s ease;
      z-index: 10;
    }

    .gallery button:hover {
      background: rgba(0,0,0,0.6);
    }

    .gallery .prev {
      left: 10px;
    }

    .gallery .next {
      right: 10px;
    }

    /* Price Section */
    .price-wrapper {
      margin: 20px 0 15px;
      font-weight: 700;
      font-size: 1.6rem;
      color: #000000;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 15px;
      flex-wrap: wrap;
      border-radius: 15px;
      padding: 15px 25px;
      /* Повернуто попередній фон для секції ціни */
      background: linear-gradient(90deg, #e0f8e9, #c2f0d3);
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
      user-select: none;
      font-family: 'Montserrat', sans-serif; /* Повернуто попередній шрифт */
    }

    .price-wrapper .new-price {
      color: #000000;
      font-size: 2rem;
      text-shadow: none;
    }

    .discount-note {
      font-weight: 700;
      font-size: 1rem;
      color: #ff4757; /* Повернуто попередній червоний для знижки */
      margin-left: 10px;
      white-space: normal;
    }

    /* Big Button */
    .big-button {
      display: inline-block;
      margin: 10px 0 10px;
      padding: 18px 32px;
      /* Повернуто попередній колір кнопки */
      background: #3498db;
      color: #fff;
      font-size: 22px;
      font-weight: 700;
      border-radius: 12px;
      text-decoration: none;
      /* Enhanced button hover effect */
      transition: background 0.3s ease, transform 0.2s ease, box-shadow 0.3s ease;
      box-shadow: 0 8px 20px rgba(52, 152, 219, 0.6);
      cursor: pointer;
    }

    .big-button:hover {
      background: #2980b9; /* Повернуто попередній темніший відтінок при наведенні */
      transform: translateY(-3px); /* Slight lift */
      box-shadow: 0 12px 25px rgba(52, 152, 219, 0.8); /* Stronger shadow on hover */
    }

    /* Timer */
    .timer {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .time-segment {
      position: relative;
      width: 90px;
      height: 90px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
    }

    .time-segment svg {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      transform: rotate(-90deg);
      z-index: 1;
      pointer-events: none;
    }

    .time-segment circle.bg {
      fill: none;
      stroke: #ddd;
      stroke-width: 8;
    }

    .time-segment circle.progress {
      fill: none;
      /* Повернуто попередній колір прогресу таймера */
      stroke: #3498db;
      stroke-width: 8;
      stroke-linecap: round;
      stroke-dasharray: 0;
      stroke-dashoffset: 0;
      transition: stroke-dashoffset 0.5s ease;
    }

    .time-segment .number {
      font-size: 1.8rem;
      line-height: 1;
      position: relative;
      z-index: 10;
      user-select: text;
      color: #0a3d62; /* Повернуто попередній глибокий синій для чисел */
      font-weight: 700;
    }

    .time-segment .label {
      margin-top: 5px;
      font-weight: 700;
      font-size: 0.9rem;
      color: #2980b9; /* Повернуто попередній синій для підписів */
      letter-spacing: 0.05em;
      user-select: none;
      position: relative;
      z-index: 10;
    }

    /* Sales Info */
    .sales-info {
      margin-bottom: 30px;
      /* Повернуто попередній фон для інформації про продажі */
      background: linear-gradient(90deg, #74ebd5, #9face6);
      padding: 20px 25px;
      border-radius: 16px;
      /* Enhanced shadow for more depth */
      box-shadow: 0 12px 30px rgba(60, 140, 210, 0.5);
      color: #0a3d62; /* Повернуто попередній глибокий синій для тексту */
      font-weight: 700;
      font-size: 1.2rem;
      display: flex;
      justify-content: center;
      gap: 30px;
      user-select: none;
      flex-wrap: wrap;
    }

    .sales-info div {
      display: flex;
      align-items: center;
      gap: 10px;
      background: white;
      border-radius: 12px;
      padding: 10px 18px;
      box-shadow: 0 6px 15px rgba(255,255,255,0.8);
      color: #2980b9; /* Повернуто попередній синій для тексту в блоках */
      font-size: 1.1rem;
    }

    .sales-info div span.icon {
      font-size: 1.6rem;
      user-select: none;
    }

    .sales-info .left-qty {
      /* Повернуто попередній фон для кількості в наявності */
      background: #ffe1e1;
      color: #c0392b; /* Повернуто попередній червоний для тексту */
      box-shadow: 0 6px 15px rgba(255,200,200,0.8);
    }

    /* Lightbox */
    .lightbox {
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(0,0,0,0.85);
      display: flex;
      justify-content: center;
      align-items: center;
      visibility: hidden;
      opacity: 0;
      transition: opacity 0.3s ease;
      z-index: 1000;
      cursor: pointer;
    }

    .lightbox.visible {
      visibility: visible;
      opacity: 1;
    }

    .lightbox img {
      max-width: 90%;
      max-height: 90%;
      border-radius: 12px;
      box-shadow: 0 0 30px #000;
      cursor: default;
    }

    /* Product Description */
    .description {
      margin-top: 10px;
      text-align: center; /* Centered text content */
    }

    .description h2 {
      color: #0a3d62; /* Повернуто попередній глибокий синій для заголовків опису */
      font-size: 22px;
      margin-bottom: 10px;
      text-align: center; /* Ensure heading is centered */
    }

    /* Стилізація абзаців як "табличних" блоків */
    .description p,
    .product-info-block p {
      color: #333;
      font-size: 16px;
      line-height: 1.6;
      text-align: center;
      background-color: #f0f8ff; /* Легкий синій фон для абзаців */
      padding: 15px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.08);
      margin-bottom: 20px; /* Відступ під абзацом */
    }

    /* Styled advantages list - making list items look like table rows/cells */
    .advantages {
      margin-top: 15px;
      padding-left: 0; /* Remove default padding */
      list-style: none; /* Remove default bullet points */
      text-align: left; /* Align list items to left within centered block */
      display: inline-block; /* Allow centering of the block itself */
      width: 100%; /* Ensure it takes full width of its parent */
    }
    .advantages li {
      font-size: 16px;
      margin-bottom: 10px;
      color: #2d3436;
      position: relative;
      padding: 12px 15px 12px 40px; /* Increased padding, especially left for icon */
      background-color: #f0f8ff; /* Light blue background for rows */
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.08); /* Subtle shadow for depth */
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }
    .advantages li:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 8px rgba(0,0,0,0.12);
    }
    /* Specific emojis for each list item */
    .advantages li::before { /* Apply common styling for all list item icons */
      position: absolute;
      left: 15px; /* Adjust position for padding */
      top: 50%;
      transform: translateY(-50%);
      font-size: 1.2em; /* Slightly larger icons */
      line-height: 1;
      content: '✅'; /* Set checkmark emoji for advantages */
    }


    /* Technical specs list */
    .technical-specs {
      list-style: none; /* Remove default bullets */
      padding-left: 0; /* Remove default padding */
    }
    .technical-specs li {
      font-size: 16px;
      margin-bottom: 10px;
      color: #333;
      position: relative;
      padding: 12px 15px; /* No left padding for icon */
      background-color: #f0f8ff; /* Consistent light blue background */
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.08);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }
    .technical-specs li:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 8px rgba(0,0,0,0.12);
    }
    .technical-specs li::before {
      content: none; /* Explicitly remove content for technical specs */
    }

    /* Apply similar styling to other product-info-block lists (Delivery and Payment) */
    /* This rule applies to ULs that are NOT .advantages or .technical-specs within .product-info-block */
    .product-info-block ul:not(.advantages):not(.technical-specs) {
      list-style: none; /* Remove default bullets */
      padding-left: 0; /* Remove default padding */
    }
    .product-info-block ul:not(.advantages):not(.technical-specs) li {
      font-size: 16px;
      margin-bottom: 10px;
      color: #333;
      position: relative;
      padding: 12px 15px 12px 40px; /* Consistent padding for icons */
      background-color: #f0f8ff; /* Consistent light blue background */
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.08);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }
    .product-info-block ul:not(.advantages):not(.technical-specs) li:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 8px rgba(0,0,0,0.12);
    }
    /* Specific emojis for Delivery and Payment */
    .product-info-block ul:not(.advantages):not(.technical-specs) li:nth-child(1)::before { content: '📦'; }
    .product-info-block ul:not(.advantages):not(.technical-specs) li:nth-child(2)::before { content: '💰'; }
    .product-info-block ul:not(.advantages):not(.technical-specs) li:nth-child(3)::before { content: '💳'; }


    /* Form */
    form {
      text-align: left;
      scroll-margin-top: 60px;
      /* Повернуто попередній фон форми */
      background-color: #000;
      padding: 25px 20px;
      border-radius: 18px;
      box-shadow: 0 18px 45px rgba(0,0,0,0.6);
      color: #fff;
      user-select: none;
    }

    /* Flex container for name and last name */
    .name-fields {
      display: flex;
      gap: 15px; /* Space between fields */
      margin-top: 18px;
      flex-wrap: wrap; /* Allow wrapping on small screens */
    }

    .name-fields > div {
        flex: 1; /* Distribute space equally */
        min-width: 120px; /* Minimum width before wrapping */
    }

    label {
      display: block;
      font-weight: 600;
      color: #f5f6fa; /* Повернуто попередній світло-сірий для написів */
      margin-bottom: 6px;
      font-size: 16px;
    }

    input[type="text"],
    input[type="tel"] {
      width: 100%;
      padding: 14px 16px;
      border-radius: 10px;
      border: 2px solid #d1d8e0; /* Повернуто попередню рамку */
      font-size: 16px;
      transition: border-color 0.3s ease;
      box-sizing: border-box;
      background-color: #222; /* Повернуто попередній фон полів */
      color: #eee;
    }

    input[type="text"]:focus,
    input[type="tel"]:focus {
      border-color: #3498db; /* Повернуто попередній синій при фокусі */
      outline: none;
      box-shadow: 0 0 8px #3498dbcc; /* Повернуто попередню тінь при фокусі */
      background-color: #111; /* Повернуто попередній фон при фокусі */
      color: #fff;
    }

    button[type="submit"] {
      margin-top: 30px;
      width: 100%;
      background-color: #27ae60; /* Збережено зелений для кнопки відправки */
      color: white;
      border: none;
      padding: 18px 0;
      font-size: 20px;
      font-weight: 700;
      border-radius: 14px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      box-shadow: 0 8px 20px rgba(39, 174, 96, 0.6);
    }

    button[type="submit"]:hover {
      background-color: #1e8449; /* Повернуто попередній темніший зелений при наведенні */
      box-shadow: 0 10px 30px rgba(39, 174, 96, 0.8);
    }

    .note {
      margin-top: 18px;
      font-size: 15px;
      color: #bdc3c7; /* Повернуто попередній світло-сірий для примітки */
      text-align: center;
      user-select: none;
    }

    /* Footer styles */
    footer {
      text-align: center;
      font-size: 14px;
      color: #ccc; /* Повернуто попередній світло-сірий для футера */
      margin-top: 40px;
      padding-bottom: 20px;
      user-select: none;
    }

    footer a {
      color: #ccc;
      text-decoration: underline;
      margin-bottom: 5px; /* Space between link and copyright */
      display: block; /* Make it a block element to take full width and center */
    }

    /* New sections styling */
    .product-media-section {
      margin-top: 30px;
      text-align: left;
      background: white;
      padding: 25px 20px;
      border-radius: 18px;
      box-shadow: 0 18px 45px rgba(0,0,0,0.15);
    }

    .product-media-section h2 {
      color: #0a3d62; /* Повернуто попередній глибокий синій для заголовків секцій */
      font-size: 22px;
      margin-bottom: 15px;
      text-align: center;
    }

    /* Single large product image styling */
    .single-product-image {
      display: block; /* Ensures it takes full width and can be centered */
      max-width: 100%; /* Ensures responsiveness */
      height: auto; /* Maintains aspect ratio */
      border-radius: 12px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
      margin: 0 auto 20px; /* Center the image and add bottom margin */
      cursor: pointer; /* Indicate it's clickable for lightbox */
      transition: transform 0.3s ease;
    }

    .single-product-image:hover {
      transform: scale(1.02); /* Slight zoom on hover */
    }


    .product-info-block { /* New class for the info blocks */
      margin-top: 30px;
      text-align: left;
      background: white;
      padding: 25px 20px;
      border-radius: 18px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1); /* Slightly reduced initial shadow */
      transform: translateY(0); /* Initial position */
      transition: all 0.3s ease-in-out; /* Smooth transition for all properties */
    }

    .product-info-block:hover {
      transform: translateY(-5px); /* Lift up slightly */
      box-shadow: 0 20px 50px rgba(0,0,0,0.25); /* More pronounced shadow on hover */
    }

    .product-info-block h2 {
      color: #0a3d62; /* Повернуто попередній глибокий синій для заголовків інформаційних блоків */
      font-size: 22px;
      margin-bottom: 15px;
      text-align: center;
    }

    /* Styles for collapsible content - NOW ALWAYS OPEN */
    .collapsible-content {
      max-height: 2000px; /* Set a large enough max-height to ensure content is always visible */
      overflow: visible; /* Allow content to overflow naturally */
      transition: none; /* No transition needed as it's always open */
    }

    /* Ensure no hover effects interfere with content visibility */
    .product-info-block:hover .collapsible-content {
      max-height: 2000px; /* Ensure it stays open on hover */
      transform: none; /* No unwanted transform */
    }


    .product-info-block ul {
      list-style: disc;
      padding-left: 20px;
    }

    .video-container {
      position: relative;
      width: 100%;
      padding-bottom: 56.25%; /* 16:9 Aspect Ratio */
      height: 0;
      overflow: hidden;
      border-radius: 12px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
      display: block; /* Ensure it takes up space */
    }

    .video-container iframe {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      border: 0;
      border-radius: 12px;
    }

    /* Buttons for navigation */
    .nav-buttons {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin-bottom: 20px; /* Space between buttons and title */
      flex-wrap: wrap; /* Allow wrapping on smaller screens */
    }

    .nav-buttons button {
      background-color: #5cb85c; /* Greenish button */
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      font-weight: 600;
      cursor: pointer;
      transition: background-color 0.3s ease, transform 0.2s ease;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .nav-buttons button:hover {
      background-color: #4cae4c;
      transform: translateY(-2px);
    }

    /* Media Queries for Responsiveness */
    @media(max-width: 520px) {
      body {
        padding: 10px;
      }
      .container {
        padding: 20px;
        margin: 20px auto;
      }
      h1 {
        font-size: 26px;
      }
      .price-wrapper {
        font-size: 1.4rem;
        padding: 10px 15px;
      }
      .price-wrapper .new-price {
        font-size: 1.8rem;
      }
      .discount-note {
        font-size: 0.9rem;
      }
      .big-button {
        padding: 15px 25px;
        font-size: 20px;
      }
      .timer {
        gap: 0.8rem;
      }
      .time-segment {
        width: 70px;
        height: 70px;
      }
      .time-segment .number {
        font-size: 1.5rem;
      }
      .time-segment .label {
        font-size: 0.8rem;
      }
      .sales-info {
        font-size: 1rem;
        gap: 15px;
        padding: 15px 20px;
      }
      .sales-info div {
        padding: 8px 12px;
        font-size: 0.95rem;
      }
      .sales-info div span.icon {
        font-size: 1.4rem;
      }
      .description h2 {
        font-size: 20px;
      }
      .description p, .advantages li {
        font-size: 15px;
      }
      form {
        padding: 20px 15px;
      }
      label {
        font-size: 15px;
      }
      input[type="text"],
      input[type="tel"] {
        padding: 12px 14px;
        font-size: 15px;
      }
      button[type="submit"] {
        padding: 15px 0;
        font-size: 18px;
      }
      .note {
        font-size: 14px;
      }
      /* New sections mobile styling */
      .product-media-section, .product-info-block {
        padding: 20px 15px;
      }
      /* Single image on mobile */
      .single-product-image {
        width: 100%;
      }
      .nav-buttons {
        gap: 10px; /* Smaller gap on mobile */
      }
      .nav-buttons button {
        font-size: 14px; /* Smaller font on mobile */
        padding: 8px 15px;
      }
    }

    /* Custom Message Box Styles */
    .message-box {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.7);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 10000;
        visibility: hidden;
        opacity: 0;
        transition: visibility 0s, opacity 0.3s ease-in-out;
    }

    .message-box.visible {
        visibility: visible;
        opacity: 1;
    }

    .message-box-content {
        background: white;
        padding: 30px;
        border-radius: 15px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        text-align: center;
        max-width: 350px;
        width: 90%;
        transform: scale(0.9);
        transition: transform 0.3s ease-in-out;
    }

    .message-box.visible .message-box-content {
        transform: scale(1);
    }

    .message-box p {
        font-size: 1.2rem;
        color: #333;
        margin-bottom: 20px;
        line-height: 1.5;
    }

    .message-box button {
        background-color: #3498db;
        color: white;
        border: none;
        padding: 12px 25px;
        border-radius: 8px;
        font-size: 1rem;
        font-weight: 600;
        cursor: pointer;
        transition: background-color 0.2s ease, transform 0.2s ease;
    }

    .message-box button:hover {
        background-color: #2980b9;
        transform: translateY(-2px);
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Navigation Buttons -->
    <div class="nav-buttons">
      <button onclick="document.getElementById('video-section').scrollIntoView({ behavior: 'smooth' })">
        ▶️ Дивитись відео
      </button>
      <button onclick="document.getElementById('description-section').scrollIntoView({ behavior: 'smooth' })">
        📝 Детальний опис
      </button>
    </div>

    <h1>☕ Кавомашина Rainberg</h1>
    <!-- Removed Rating Section -->
    <!--
    <div class="rating">
      <span class="stars">★★★★☆</span>
      <span class="score">4.6</span>
      <span class="reviews">(123 відгуки)</span>
    </div>
    -->

    <div class="gallery" aria-label="Галерея зображень кавомашини">
      <button class="prev" aria-label="Попереднє зображення">&#10094;</button>
      <button class="next" aria-label="Наступне зображення">&#10095;</button>
      <!-- Real images for main gallery -->
      <img src="https://images.prom.ua/6715459781_w640_h640_kofevarka-professionalnaya-dlya.jpg" alt="Кавомашина Rainberg - З коробкою" class="active" />
      <img src="https://images.prom.ua/6736106186_w640_h640_kapelnaya-kompaktnaya-kofevarka.jpg" alt="Кавомашина Rainberg - Вигляд збоку" />
      <img src="https://images.prom.ua/6715459667_w640_h640_kofevarka-professionalnaya-dlya.jpg" alt="Кавомашина Rainberg - Зблизька" />
      <img src="https://images.prom.ua/6715459664_w640_h640_kofevarka-professionalnaya-dlya.jpg" alt="Кавомашина Rainberg - Загальний вигляд" />
      <img src="https://images.prom.ua/6686538628_w640_h640_kofevarka-s-nasadkoj.jpg" alt="Кавомашина Rainberg - Додаткове фото" />
      <img src="https://images.prom.ua/6228078262_w640_h640_kofevarka-rozhkovaya-rainberg.jpg" alt="Кавомашина Rainberg - Назва фірми" />
    </div>

    <div class="price-wrapper" aria-label="Ціна товару">
      <del>2300 грн</del>
      <span class="new-price">1599 грн</span>
      <span class="discount-note">🔥 — Акційна ціна! Знижка діє обмежений час!</span>
    </div>

    <a href="#order" class="big-button">🛒 Замовити зі знижкою</a>

    <div class="timer" aria-label="Таймер зворотного відліку знижки">
      <div class="time-segment" id="segment-days">
        <svg viewBox="0 0 100 100">
          <circle class="bg" cx="50" cy="50" r="46"></circle>
          <circle class="progress" cx="50" cy="50" r="46"></circle>
        </svg>
        <div class="number" id="days">00</div>
        <div class="label">Днів</div>
      </div>
      <div class="time-segment" id="segment-hours">
        <svg viewBox="0 0 100 100">
          <circle class="bg" cx="50" cy="50" r="46"></circle>
          <circle class="progress" cx="50" cy="50" r="46"></circle>
        </svg>
        <div class="number" id="hours">00</div>
        <div class="label">Годин</div>
      </div>
      <div class="time-segment" id="segment-minutes">
        <svg viewBox="0 0 100 100">
          <circle class="bg" cx="50" cy="50" r="46"></circle>
          <circle class="progress" cx="50" cy="50" r="46"></circle>
        </svg>
        <div class="number" id="minutes">00</div>
        <div class="label">Хвилин</div>
      </div>
      <div class="time-segment" id="segment-seconds">
        <svg viewBox="0 0 100 100">
          <circle class="bg" cx="50" cy="50" r="46"></circle>
          <circle class="progress" cx="50" cy="50" r="46"></circle>
        </svg>
        <div class="number" id="seconds">00</div>
        <div class="label">Секунд</div>
      </div>
    </div>

    <div class="sales-info" aria-label="Інформація про продажі">
      <div class="sold-today">
        <span class="icon">✅</span>
        Куплено: <strong>347 штук</strong> 🎉
      </div>
      <div class="left-qty">
        <span class="icon">⚠️</span>
        У наявності: <strong>5 штук</strong> ❗
      </div>
    </div>

    <div class="description product-info-block" id="description-section">
      <h2>Опис товару</h2>
      <div class="collapsible-content">
        <p>
          Кавомашина Rainberg — це ідеальне рішення для любителів справжнього еспресо та капучино вдома.
          Завдяки потужності 2200 Вт, вона швидко приготує ароматну каву з густою пінкою.
          Компактний розмір дозволяє їй ідеально вписатися в будь-яку кухню.
        </p>

        <ul class="advantages">
          <li class="advantage-item-1">Готує досконалий еспресо з багатою пінкою</li>
          <li class="advantage-item-2">Вбудований капучинатор для молочних напоїв</li>
          <li class="advantage-item-3">Висока потужність 2200 Вт для швидкого нагріву</li>
          <li class="advantage-item-4">Компактний та стильний дизайн</li>
          <li class="advantage-item-5">Простота у використанні та догляді</li>
        </ul>

        <h3>Технічні характеристики:</h3>
        <ul class="technical-specs">
          <li>Тип: Кавоварка еспресо</li>
          <li>Потужність: 2200 Вт</li>
          <li>Тиск пари: 3.5 бар</li>
          <li>Мірна ложка: 21 г</li>
          <li>Знімна насадка для спінювання та піддон для легкого очищення</li>
          <li>Режими роботи: еспресо, капучино</li>
          <li>Захист від перегріву</li>
          <li>Індикатор роботи</li>
        </ul>
      </div>
    </div>

    <!-- New image before "Why Buy" section -->
    <div class="product-media-section">
        <img id="main-product-display-image" src="https://ireland.apollo.olxcdn.com/v1/files/b3p65ylrs2ty1-UA/image;s=1000x700" alt="Додаткове фото кавомашини" class="single-product-image" />
    </div>

    <!-- New Section: Video Review -->
    <div class="product-media-section" id="video-section">
      <h2>Відео-огляд</h2>
      <div class="video-container">
        <!-- YouTube video embedded here -->
        <iframe src="https://www.youtube.com/embed/ppWteXyN2F4" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>

    <!-- New Section: Delivery and Payment Information -->
    <div class="product-info-block">
      <h2>Доставка та Оплата</h2>
      <div class="collapsible-content">
        <p>
          Доставка здійснюється Новою Поштою по всій Україні. Зазвичай це займає 1-3 робочі дні.
          Оплата можлива при отриманні (накладений платіж) або передоплатою на картку.
          Вартість доставки розраховується за тарифами перевізника.
        </p>
        <ul>
          <li>📦 Швидка доставка Новою Поштою</li>
          <li>💰 Оплата при отриманні (післяплата)</li>
          <li>💳 Можлива передоплата на картку</li>
        </ul>
      </div>
    </div>

    <!-- New Section: Warranty and Returns -->
    <div class="product-info-block">
      <h2>Гарантія та Повернення</h2>
      <div class="collapsible-content">
        <p>
          На всі наші кавомашини діє гарантія 12 місяців з моменту покупки.
          Ви маєте право повернути товар протягом 14 днів з моменту отримання, якщо він не підійшов або має дефекти.
          Для оформлення повернення або звернення по гарангії, будь ласка, зв'яжіться з нами.
        </p>
        <ul>
          <li>✅ 12 місяців гарантії</li>
          <li>🔄 Повернення протягом 14 днів</li>
          <li>📞 Професійна підтримка клієнтів</li>
        </ul>
      </div>
    </div>

    <form id="order" aria-label="Форма замовлення">
      <div class="name-fields">
        <div>
          <label for="name">Ім'я 🧑‍</label>
          <input type="text" id="name" name="name" required placeholder="Ваше ім'я" autocomplete="name" />
        </div>
        <div>
          <label for="lastName">Прізвище 👨‍🦰</label>
          <input type="text" id="lastName" name="lastName" required placeholder="Ваше прізвище" autocomplete="family-name" />
        </div>
      </div>

      <label for="phone">Телефон 📞</label>
      <input type="tel" id="phone" name="phone" required placeholder="+38 (___) ___-__-__" autocomplete="tel" pattern="\+?\d{7,15}" />

      <label for="city">Місто 🏙️</label>
      <input type="text" id="city" name="city" required placeholder="Ваше місто" autocomplete="address-level2" />

      <label for="department">Відділення Нової Пошти 📦</label>
      <input type="text" id="department" name="department" required placeholder="Номер відділення" autocomplete="off" />

      <button type="submit">✅ Замовити кавомашину</button>
      <div class="note">Ми зв'яжемося з вами найближчим часом! 📲</div>
    </form>
  </div>

  <div class="lightbox" id="lightbox" role="dialog" aria-modal="true" aria-label="Перегляд фото">
    <img src="" alt="Збільшене фото" />
  </div>

  <!-- Custom Message Box HTML -->
  <div class="message-box" id="customMessageBox">
      <div class="message-box-content">
          <p id="messageBoxText"></p>
          <button id="messageBoxClose">ОК</button>
      </div>
  </div>

  <!-- Footer Section -->
  <footer>
    <a href="#privacy-policy" style="color: #ccc; text-decoration: underline; margin-bottom: 5px; display: block;">Політика конфіденційності</a>
    <p>&copy; <span id="currentYear"></span> Всі права захищені.</p>
  </footer>

  <script>
    // Helper function to show custom message box
    function showMessageBox(message) {
        const messageBox = document.getElementById('customMessageBox');
        const messageBoxText = document.getElementById('messageBoxText');
        messageBoxText.textContent = message;
        messageBox.classList.add('visible');
    }

    // Close custom message box
    document.getElementById('messageBoxClose').addEventListener('click', () => {
        document.getElementById('customMessageBox').classList.remove('visible');
    });

    // Gallery photos (main product gallery)
    const gallery = document.querySelector('.gallery');
    const images = gallery.querySelectorAll('img');
    const prevBtn = gallery.querySelector('.prev');
    const nextBtn = gallery.querySelector('.next');
    let currentIndex = 0;

    function showImage(index) {
      images.forEach((img, i) => {
        img.classList.toggle('active', i === index);
      });
      currentIndex = index;
    }

    prevBtn.addEventListener('click', () => {
      let newIndex = currentIndex - 1;
      if (newIndex < 0) newIndex = images.length - 1;
      showImage(newIndex);
    });

    nextBtn.addEventListener('click', () => {
      let newIndex = currentIndex + 1;
      if (newIndex >= images.length) newIndex = 0;
      showImage(newIndex);
    });

    // Lightbox for the single large product photo
    const mainProductDisplayImage = document.getElementById('main-product-display-image');
    const lightbox = document.getElementById('lightbox');
    const lightboxImg = lightbox.querySelector('img');

    // Function to handle image clicks for the single large image
    if (mainProductDisplayImage) { // Check if the element exists
        mainProductDisplayImage.addEventListener('click', (e) => {
            lightboxImg.src = e.target.src;
            lightbox.classList.add('visible');
        });
    }

    lightbox.addEventListener('click', () => {
      lightbox.classList.remove('visible');
      lightboxImg.src = '';
    });

    // Countdown Timer Logic
    let endTime; // Declare endTime globally or in a scope accessible by updateTimer

    function initializeTimer() {
        // Try to get endTime from localStorage
        const storedEndTime = localStorage.getItem('timerEndTime');
        if (storedEndTime) {
            endTime = new Date(storedEndTime);
            // If the stored time is in the past, reset it
            if (endTime.getTime() < new Date().getTime()) {
                resetTimer();
            }
        } else {
            // If no time is stored, set a new one
            resetTimer();
        }
        // Start updating the timer
        setInterval(updateTimer, 1000);
        updateTimer(); // Initial call to display timer immediately
    }

    function resetTimer() {
        const now = new Date();
        // Set timer to 10 hours from now
        endTime = new Date(now.getTime() + (10 * 60 * 60 * 1000)); // 10 hours in milliseconds
        localStorage.setItem('timerEndTime', endTime.toISOString()); // Store as ISO string
    }

    const daysCircle = document.querySelector('#segment-days .progress');
    const hoursCircle = document.querySelector('#segment-hours .progress');
    const minutesCircle = document.querySelector('#segment-minutes .progress');
    const secondsCircle = document.querySelector('#segment-seconds .progress');

    // Define the radius for the SVG circles
    const circleRadius = 46; // This matches the 'r' attribute in the SVG circles
    // Calculate the full circumference based on this radius
    const fullDash = 2 * Math.PI * circleRadius;

    // Set the stroke-dasharray for all progress circles initially
    daysCircle.style.strokeDasharray = fullDash;
    hoursCircle.style.strokeDasharray = fullDash;
    minutesCircle.style.strokeDasharray = fullDash;
    secondsCircle.style.strokeDasharray = fullDash;


    function updateTimer() {
      const now = new Date();
      let diff = (endTime - now) / 1000; // Difference in seconds

      if (diff <= 0) { // Changed to less than or equal to 0
        diff = 0;
        resetTimer(); // Reset timer when it reaches zero
        // No need to return here, let it update with new values
      }

      const days = Math.floor(diff / 86400);
      const hours = Math.floor((diff % 86400) / 3600);
      const minutes = Math.floor((diff % 3600) / 60);
      const seconds = Math.floor(diff % 60);

      document.getElementById('days').textContent = days.toString().padStart(2, '0');
      document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
      document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
      document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');

      // Update circle progress
      function calcOffset(value, max) {
        return max > 0 ? fullDash - (value / max) * fullDash : fullDash;
      }

      // Max values for each segment
      const maxDays = 365; // Assuming a max of 365 days for the circle
      const maxHours = 24;
      const maxMinutes = 60;
      const maxSeconds = 60;

      daysCircle.style.strokeDashoffset = calcOffset(days, maxDays);
      hoursCircle.style.strokeDashoffset = calcOffset(hours, maxHours);
      minutesCircle.style.strokeDashoffset = calcOffset(minutes, maxMinutes);
      secondsCircle.style.strokeDashoffset = calcOffset(seconds, maxSeconds);
    }

    // Initialize the timer when the page loads
    window.onload = initializeTimer;

    // Scroll to order form on button click
    document.querySelector('.big-button').addEventListener('click', e => {
      e.preventDefault();
      document.getElementById('order').scrollIntoView({ behavior: 'smooth' });
    });

    // Function to send data to Telegram bot
    async function sendOrderToBot(formData) {
        const BOT_TOKEN = '7908669044:AAGaETeXAwZGUz1fkLxPfwnql5ktjOkhJpk'; // ВАШ БОТ-ТОКЕН
        const CHAT_ID = '5867301828';     // ВАШ CHAT_ID

        // Отримуємо назву товару з заголовка h1
        const productName = document.querySelector('h1').textContent.trim();

        const message = `
        ⚡️ НОВЕ ЗАМОВЛЕННЯ! ⚡️

        Товар: ${productName}
        Ім'я: ${formData.name}
        Прізвище: ${formData.lastName}
        Телефон: ${formData.phone}
        Місто: ${formData.city}
        Відділення Нової Пошти: ${formData.department}

        Ціна: 1599 грн (акційна)
        `;

        const telegramApiUrl = `https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`;

        try {
            const response = await fetch(telegramApiUrl, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({
                    chat_id: CHAT_ID,
                    text: message
                })
            });

            if (response.ok) {
                console.log('Дані успішно відправлені в Telegram.');
                showMessageBox('Дякуємо за замовлення! Ми зв\'яжемося з вами найближчим часом. 📲'); // Re-added showMessageBox
            } else {
                const errorData = await response.json();
                console.error('Помилка відправки даних в Telegram:', errorData);
                showMessageBox('Помилка при відправці замовлення. Спробуйте ще раз або зв\'яжіться з нами напряму.'); // Re-added showMessageBox
            }
        } catch (error) {
            console.error('Помилка мережі при відправці в Telegram:', error);
            showMessageBox('Помилка підключення. Перевірте ваше інтернет-з\'єднання.'); // Re-added showMessageBox
        }
    }

    // Form submission
    const orderForm = document.getElementById('order');
    orderForm.addEventListener('submit', async e => {
      e.preventDefault();

      // Збираємо дані форми
      const formData = {
        name: document.getElementById('name').value,
        lastName: document.getElementById('lastName').value, // Get last name
        phone: document.getElementById('phone').value,
        city: document.getElementById('city').value,
        department: document.getElementById('department').value
      };

      // Відправляємо дані в Telegram-бот
      await sendOrderToBot(formData);

      // Очищаємо форму
      orderForm.reset();
    });

    // Set current year in footer
    document.getElementById('currentYear').textContent = new Date().getFullYear();
  </script>
</body>
</html>
