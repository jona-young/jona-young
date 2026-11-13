# Hi there, I'm Jonathan 👋

I'm a **Full-Stack Software Engineer** based in the Greater Toronto Area. I build and run production web applications end to end: features, databases, payment integrations, automated tests, CI pipelines, data reporting, and the servers they run on.

My main codebase powers a live commercial platform, so it lives in a private repository. Below is an overview of how it's built, tested, and deployed.

---

## 🛠️ Tech Stack
* **Languages:** TypeScript, JavaScript, Python, SQL (PostgreSQL)
* **Frameworks & Libraries:** Next.js, React, Node.js, Express, Prisma ORM, Pandas, NumPy
* **Testing & CI/CD:** Vitest, Playwright, Selenium, GitHub Actions
* **Data & BI:** PostgreSQL, MongoDB, Power BI, Excel/CSV ETL with Pandas
* **Cloud & DevOps:** DigitalOcean (Droplets, Managed DBs), AWS (EC2), Ubuntu Server, Nginx, Linux CLI
* **Integrations:** PayPal Invoicing API, Twilio SMS, Resend, REST APIs & Webhooks
* **AI Tools:** Claude Code

---

## 🏗️ Case Study: Order & Billing Platform
*The repository is private to protect transaction infrastructure and customer data. I'm happy to walk through the codebase during technical interviews.*

I built an order-intake and fulfillment platform from scratch for my climbing shoe resole business. It processed **250–300 orders in the past year** and **$25K–$35K in customer revenue** over two years, with PayPal as the payment provider.

### 📐 System Design

```text
          [ Next.js / TypeScript UI ] ──(HTTPS)──> [ Nginx Reverse Proxy ]
                                                              │
                                                   (Ubuntu / DigitalOcean)
                                                              │
                                                              ▼
[ Resend Email / Twilio SMS ] <──(notifications)── [ Next.js Server Core ] ──(create invoice)───> [ PayPal Invoicing API ]
                                                                           <──(signed webhooks)──
                                                              │
                                                        (Prisma ORM)
                                                              │
                                                              ▼
                                                   [ Managed PostgreSQL ]
                                                              │
                                                         (reporting)
                                                              ▼
                                                   [ Power BI Dashboard ]
```

### 🚀 Delivery Pipeline

```text
[ Pull Request ] ──> [ GitHub Actions: lint · type check · unit tests · E2E tests ]
                                                    │
                                        (all checks pass → merge)
                                                    │
                                                    ▼
                                 [ Production deploy (off-peak hours) ]
```

### ⚡ Key Engineering Work
* **Infrastructure:** Provisioned and maintain Ubuntu servers on DigitalOcean, including Nginx reverse proxy routing and SSL/TLS certificates.
* **Billing:** Integrated the **PayPal Invoicing API** into the server layer as the business's billing pipeline, using **Prisma** to store invoice metadata and payment status in **PostgreSQL**.
* **Idempotency:** Made invoice creation idempotent so retries and duplicate submissions can never double-bill a customer, with tests that prove it.
* **Webhook Security:** Every incoming PayPal webhook's signature is verified through PayPal's verification API before it can update an order.
* **Event-Driven Notifications:** Webhook handlers listen for payment confirmations, update order records, and trigger customer updates through **Resend** (email) and **Twilio** (SMS).
* **Testing:** Unit tests with **Vitest** for business logic and payload parsing, plus end-to-end tests with **Playwright** covering checkout, invoicing, and order-status flows.
* **CI/CD:** A **GitHub Actions** pipeline runs linting, TypeScript type checks, and the full test suite on every pull request; failing checks block the merge.
* **Incident Response:** When a bug in payload parsing halted invoice creation, a manual-invoice fallback I'd built in advance kept every order on schedule. I shipped the fix and added regression tests so it can't recur.

### 📊 Business Reporting
* Connected **Power BI** to the platform's PostgreSQL database and built a dashboard tracking annual revenue and order counts, monthly order volume, orders per customer, and median turnaround times between key order stages.

---

## 🧪 Earlier Work: Operations Automation
Self-taught while working as an administrator at a private racquet club, where I automated my own workflows:
* **ETL & reporting:** Python scripts extracted Excel data, transformed it with **Pandas**, and produced reports, charts, and tables for the sports department, scheduled with Windows Task Scheduler.
* **Rule enforcement:** Headless **Selenium** scripts enforced court rules (no-shows, late cancellations, and other violations) across the court booking system and membership database, logged offenses weekly into a per-member tracking database, and sent members alert emails.
* **Internal tools:** Built a purchase order web app (MongoDB, Express, React, Node.js on AWS EC2) that replaced a paper process for 10–12 staff, and rolled it out by running the paper and app processes in parallel to validate it with users.

---

📫 **Let's connect:** [LinkedIn](https://www.linkedin.com/in/jonayoung) · young.jon@icloud.com
