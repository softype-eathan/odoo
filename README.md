# Odoo

[![Build Status](https://runbot.odoo.com/runbot/badge/flat/1/master.svg)](https://runbot.odoo.com/runbot)
[![Tech Doc](https://img.shields.io/badge/master-docs-875A7B.svg?style=flat&colorA=8F8F8F)](https://www.odoo.com/documentation/master)
[![Help](https://img.shields.io/badge/master-help-875A7B.svg?style=flat&colorA=8F8F8F)](https://www.odoo.com/forum/help-1)
[![Nightly Builds](https://img.shields.io/badge/master-nightly-875A7B.svg?style=flat&colorA=8F8F8F)](https://nightly.odoo.com/)

Odoo is a suite of web based open source business apps.

The main Odoo Apps include an [Open Source CRM](https://www.odoo.com/page/crm),
[Website Builder](https://www.odoo.com/app/website),
[eCommerce](https://www.odoo.com/app/ecommerce),
[Warehouse Management](https://www.odoo.com/app/inventory),
[Project Management](https://www.odoo.com/app/project),
[Billing &amp; Accounting](https://www.odoo.com/app/accounting),
[Point of Sale](https://www.odoo.com/app/point-of-sale-shop),
[Human Resources](https://www.odoo.com/app/employees),
[Marketing](https://www.odoo.com/app/social-marketing),
[Manufacturing](https://www.odoo.com/app/manufacturing),
[...](https://www.odoo.com/)

Odoo Apps can be used as stand-alone applications, but they also integrate seamlessly so you get
a full-featured [Open Source ERP](https://www.odoo.com) when you install several Apps.

## Getting started with Odoo

For a standard installation please follow the [Setup instructions](https://www.odoo.com/documentation/master/administration/install/install.html)
from the documentation.

### Docker Setup (Recommended for Development)

This repository includes a Docker Compose configuration for running PostgreSQL.

1. **Start the PostgreSQL container:**
   ```bash
   docker-compose up -d postgres
   ```

2. **Install Python dependencies:**
   ```bash
   # Create a virtual environment (Python 3.12 or 3.13 recommended)
   python -m venv venv

   # Activate the virtual environment
   # On Windows:
   venv\Scripts\activate
   # On Linux/Mac:
   source venv/bin/activate

   # Install psycopg2-binary first
   pip install psycopg2-binary

   # Install remaining dependencies
   pip install -r requirements.txt
   ```

3. **Configure Odoo to connect to PostgreSQL:**

   Edit `odoo.conf` to match your Docker PostgreSQL credentials:
   ```ini
   [options]
   db_host = localhost
   db_port = 5432
   db_user = odoo
   db_password = odoo
   addons_path = addons,odoo/addons
   ```

4. **Start Odoo:**
   ```bash
   python odoo-bin -c odoo.conf
   ```

5. **Access Odoo:**

   Open your browser and navigate to `http://localhost:8069`

6. **Create a database:**

   Use the web interface to create your first database, or use the command line:
   ```bash
   python odoo-bin -c odoo.conf -d mydb -i base --stop-after-init
   ```

To learn the software, we recommend the [Odoo eLearning](https://www.odoo.com/slides),
or [Scale-up, the business game](https://www.odoo.com/page/scale-up-business-game).
Developers can start with [the developer tutorials](https://www.odoo.com/documentation/master/developer/howtos.html).

## Security

If you believe you have found a security issue, check our [Responsible Disclosure page](https://www.odoo.com/security-report)
for details and get in touch with us via email.
