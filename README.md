# Phishing Awareness Training

An interactive, single-page training module that teaches people how to recognize and avoid phishing attacks. It covers phishing emails, fake websites, social engineering tactics, real-world incidents and best practices, with hands-on exercises and quizzes throughout.

**Live demo:** `https://<your-username>.github.io/phishing-awareness-training/`
*(replace `<your-username>` after enabling GitHub Pages, see [Deployment](#deployment))*

---

## Table of contents

- [Overview](#overview)
- [Features](#features)
- [Module outline](#module-outline)
- [Interactive elements](#interactive-elements)
- [Getting started](#getting-started)
- [Deployment](#deployment)
- [Project structure](#project-structure)
- [Customizing the content](#customizing-the-content)
- [Design and accessibility](#design-and-accessibility)
- [Sources and disclaimer](#sources-and-disclaimer)
- [License](#license)

---

## Overview

Phishing is one of the most common ways attackers gain access to people, accounts and organizations, because it targets human behavior rather than software. This project turns that topic into a short, self-paced course of about 25 minutes.

Learners work through six teaching sections and a final assessment. Each section explains a concept, lets the learner practice it, and finishes with a short quiz that gives immediate feedback.

**Who it is for:** students, employees, and anyone who wants a practical introduction to phishing. No technical background is needed.

## Features

- **Learn by doing:** the module opens with an email to inspect, and every section includes something to click, test or answer.
- **Instant feedback:** every quiz answer shows a short explanation of why it is right or wrong.
- **Score tracking:** points accumulate in the sidebar, and the final assessment reports a pass or fail result (8 out of 10 to pass).
- **Real incidents:** five documented attacks, each ending with a practical lesson.
- **Works anywhere:** one HTML file, no build step, no dependencies, no network requests.
- **Private by design:** nothing is stored, tracked or sent anywhere.

## Module outline

| # | Section | What learners do |
|---|---------|------------------|
| Intro | Inspect a suspicious email | Click seven red flags in a fake message |
| 1 | What phishing is | Learn the main attack types, then take a quiz |
| 2 | Spotting phishing emails | Apply a checklist, play "phish or legit?" (6 messages), take a quiz |
| 3 | Spotting fake websites | Analyze addresses with the URL inspector, take a quiz |
| 4 | Social engineering | Flip through 8 manipulation tactics and their counter-measures, take a quiz |
| 5 | Real-world examples | Read five case studies with lessons, take a quiz |
| 6 | Best practices | Tick a habit checklist, learn the steps to take after a mistake |
| 7 | Final assessment | Answer 10 mixed questions and get a result |

### Topics covered

- **Attack types:** phishing, spear phishing, whaling and business email compromise, smishing (SMS), vishing (voice), quishing (QR codes)
- **Email red flags:** spoofed senders, lookalike domains, urgency, generic greetings, disguised links, dangerous attachments
- **Fake website signs:** typosquatting, brand names in subdomains, punycode, `@` tricks, IP addresses, URL shorteners, why the padlock does not prove safety
- **Social engineering:** urgency, authority, fear, reward, curiosity, helpfulness, pretexting, baiting and tailgating
- **Defenses:** password managers, multi-factor authentication and passkeys, out-of-band verification, prompt reporting
- **Case studies:** Target (2013), Google and Facebook invoice fraud (2013 to 2015), Podesta email compromise (2016), Twitter (2020), Uber (2022)

## Interactive elements

- **Red-flag hunt:** a realistic phishing email where each suspicious detail is clickable and explained.
- **Phish or legit game:** six sample messages, with an explanation after every choice.
- **URL inspector:** paste any address and see the real registered domain highlighted, a risk verdict and a list of findings. It runs entirely in the browser and never opens the link.
- **Flip cards:** eight social engineering tactics, each with a real-life example and how to counter it.
- **Quizzes:** six quizzes with instant feedback, plus a scored final assessment with retry.
- **Habit checklist:** ten practical habits to commit to.

## Getting started

No installation is required.

**Option 1: open the file**

1. Download or clone the repository.
2. Open `index.html` in any modern browser.

**Option 2: clone with Git**

```bash
git clone https://github.com/<your-username>/phishing-awareness-training.git
cd phishing-awareness-training
```

Then open `index.html` in your browser. To serve it locally instead:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Deployment

The site is static, so it can be hosted for free with GitHub Pages.

1. Push `index.html` to the `main` branch.
2. In the repository, go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute or two the site is available at `https://<your-username>.github.io/phishing-awareness-training/`.

## Project structure

```
phishing-awareness-training/
├── index.html    # The complete module: content, styles and scripts
└── README.md     # This file
```

Everything lives in a single file on purpose, so the module is easy to share, host and hand in.

## Customizing the content

All content is plain HTML and JavaScript inside `index.html`.

- **Quiz questions:** edit the `Q` object in the script section. Each question has the text, an options array `o`, the index of the correct answer `a`, and an explanation `w`.
- **Phish or legit messages:** edit the `PL` array.
- **URL inspector rules:** edit the `BRANDS`, `RISKY_TLD` and `SHORT` lists and the checks inside the `inspect` function.
- **Social engineering cards:** edit the `TAC` array.
- **Habit checklist:** edit the `CL` array.
- **Pass mark:** change the `r>=8` condition in the `showCert` function.
- **Colors and fonts:** change the CSS variables at the top of the `<style>` block. Dark mode values are defined separately.

## Design and accessibility

- Responsive layout with a sidebar on desktop and a top navigation strip on mobile
- Automatic light and dark mode, with a manual toggle
- Keyboard-accessible buttons with visible focus outlines
- Respects the "reduce motion" system setting
- No external fonts, scripts, images or tracking

## Sources and disclaimer

- All example emails, senders and links are **fictional** and created for training purposes only.
- Case studies are summarized from publicly reported incidents. Details are simplified, so consult the original reporting before citing figures.
- This module is educational. Always follow your own organization's security and incident reporting procedures.

## License

Released under the MIT License. Add a `LICENSE` file to the repository if you want to make this explicit.
