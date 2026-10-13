# Hi there, I'm Jonathan 👋

I am a system-driven **Full-Stack Engineer** based in the Greater Toronto Area. I specialize in building production-grade web applications, deploying secure cloud infrastructure, and engineering resilient browser automation pipelines. 

As a **Technical Founder**, my primary codebases operate live, commercial platforms and sit in secure, private repositories. Below is an architectural blueprint of the systems I design and maintain.

---

## 🛠️ Tech Stack & Core Competencies
* **Languages:** TypeScript, JavaScript, Python, SQL (PostgreSQL)
* **Frameworks & Libraries:** Next.js, React, Node.js, Express, NumPy
* **Cloud & DevOps:** DigitalOcean (Droplets, Managed DBs), AWS (EC2), Ubuntu Server, Nginx Reverse Proxies, Linux CLI
* **Automation & Testing:** Playwright, Selenium, Browser Automation Scripting, API Lifecycle Testing
* **Integrated Engines:** PayPal Invoicing API, Twilio SMS Engine, Resend Transactional Mailers

---

## 🏗️ Core Architecture Case Study: Commercial E-Commerce Platform
*Note: The repository for this platform is private to protect transaction infrastructure and customer data. A guided codebase walkthrough is available upon request during technical interviews.*

I engineered an asynchronous order-intake and customer fulfillment web application from scratch that has securely processed **\$20K–\$30K in consumer transactions** over a 2-year lifecycle.

### 📐 System Design Blueprint

```text
 [ Next.js / TypeScript UI ] ──(HTTPS)──> [ Nginx Reverse Proxy ]
                                                         │
                                                 (Ubuntu / Droplets)
                                                         │
                                                         ▼
[ Resend Email / Twilio SMS ] <──(Notifications)── [ Next.js Server Core ] ──(Payments)──> [ PayPal Invoicing API ]
                                                         │
                                                    (Prisma ORM)
                                                         │
                                                         ▼
                                                [ Managed PostgreSQL ]
```

### ⚡ Key Engineering Achievements:
* **Infrastructure Layout:** Provisioned and configured self-hosted **Ubuntu Server droplets on DigitalOcean**, managing Nginx configuration blocks, reverse proxy routing, and SSL/TLS certificate updates.
* **Financial & State Orchestration:** Programmatically integrated the **PayPal Invoicing API** within the **Next.js Server Core** to serve as the primary billing pipeline for a physical service business; utilized **Prisma ORM** to capture unique invoice metadata and securely log payment tokens to a **Managed PostgreSQL database**, enabling the seamless collection of **$20K–$30K in revenue**.
* **Event-Driven Communications:** Engineered custom asynchronous webhook handlers inside the server routing layer to listen for payment confirmations, updating relational database schemas and instantly triggering customer milestones via the **Resend** and **Twilio** APIs.


---

## 🧪 Automation Sandbox: Python & Selenium
* Built custom scripting workflows designed to eliminate manual data entry. Parses tabular structures (Excel/NumPy arrays) and programmatically drives browser behavior using Selenium to automate operational compliance pipelines.

📫 **Let's Connect:** https://www.linkedin.com/in/jonayoung | young.jon@icloud.com
