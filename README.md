# Hi there, I'm Jonathan 👋

I'm a **Full-Stack Software Engineer** based in the Greater Toronto Area. I build and run production web applications end to end: features, databases, payment integrations, automated tests, CI pipelines, and the servers they run on.

My main codebase powers a live commercial platform, so it lives in a private repository. Below is an overview of how it's built, tested, and deployed.

---

## 🛠️ Tech Stack
* **Languages:** TypeScript, JavaScript, Python, SQL (PostgreSQL)
* **Frameworks & Libraries:** Next.js, React, Node.js, Express, Prisma ORM, Pandas, NumPy
* **Testing & CI/CD:** Vitest, Playwright, Selenium, GitHub Actions
* **Cloud & DevOps:** DigitalOcean (Droplets, Managed DBs), AWS (EC2), Ubuntu Server, Nginx, Linux CLI
* **Integrations:** PayPal Invoicing API, Twilio SMS, Resend, REST APIs & Webhooks
* **AI Tools:** Claude Code

---

## 🏗️ Case Study: Order & Payments Platform
*The repository is private to protect transaction infrastructure and customer data. I'm happy to walk through the codebase during technical interviews.*

I built an order-intake and fulfillment platform from scratch that has processed **$25K–$35K in customer revenue** over two years.

### 📐 System Design

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

### 🚀 Delivery Pipeline

```text
 [ Pull Request ] ──> [ GitHub Actions: lint · type check · unit tests · E2E tests ]
                                                         │
                                                  (all checks pass)
                                                         │
                                                         ▼
                                     [ Production deploy (off-peak hours) ]
```

### ⚡ Key Engineering Work
* **Infrastructure:** Provisioned and maintain Ubuntu servers on DigitalOcean, including Nginx reverse proxy routing and SSL/TLS certificates.
* **Payments:** Integrated the **PayPal Invoicing API** into the server layer as the business's billing pipeline, using **Prisma** to store invoice metadata and payment status in **PostgreSQL**.
* **Event-Driven Notifications:** Built webhook handlers that listen for payment confirmations, update order records, and trigger customer updates through **Resend** (email) and **Twilio** (SMS).
* **Testing:** Unit tests with **Vitest** for business logic and payload parsing, plus end-to-end tests with **Playwright** covering checkout, invoicing, and order-status flows.
* **CI/CD:** A **GitHub Actions** pipeline runs linting, TypeScript type checks, and the full test suite on every pull request; failing checks block the merge. Releases are validated in staging before going to production.
* **Incident Response:** When a bug in payload parsing halted invoice creation, a manual-invoice fallback I'd built in advance kept every order on schedule. I shipped the fix and added regression tests so it can't recur.

---

## 🧪 Automation: Python & Selenium
* Built Python scripts that parse spreadsheet data with **Pandas** and drive browser workflows with **Selenium**, automating compliance tasks and sending targeted email alerts in place of manual data entry.

---

📫 **Let's connect:** [LinkedIn](https://www.linkedin.com/in/jonayoung) · young.jon@icloud.com
