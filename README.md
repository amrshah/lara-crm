# AlamiaConnect CRM

AlamiaConnect CRM is a powerful Customer Relationship Management system based on Krayin CRM.

## Topics

1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Installation & Configuration](#installation-and-configuration)
4. [License](#license)
5. [Attribution](#attribution)

### Introduction

AlamiaConnect CRM is built on top of [Krayin CRM](https://krayincrm.com), utilizing technologies such as [Laravel](https://laravel.com) and [Vue.js](https://vuejs.org).

**A complete customer lifecycle management solution.**

It packs in lots of features that will allow your business to scale in no time:

-   Descriptive and Simple Admin Panel.
-   Admin Dashboard.
-   Custom Attributes.
-   Built on Modular Approach.
-   Email parsing via Sendgrid.

### Documentation

For the underlying framework documentation, refer to [Krayin CRM Docs](https://devdocs.krayincrm.com).

### Requirements

-   **SERVER**: Apache 2 or NGINX.
-   **RAM**: 3 GB or higher.
-   **PHP**: 8.1 or higher
-   **For MySQL users**: 5.7.23 or higher.
-   **For MariaDB users**: 10.2.7 or Higher.
-   **Node**: 8.11.3 LTS or higher.
-   **Composer**: 2.5 or higher

### Installation and Configuration

##### Execute these commands below, in order

```
composer create-project
```

-   Find **.env** file in root directory and change the **APP_URL** param to your **domain**.

-   Also, Configure the **Mail** and **Database** parameters inside **.env** file.

```
php artisan krayin-crm:install
```

**To execute Krayin**:

##### On server:

Warning: Before going into production mode we recommend you uninstall developer dependencies.
In order to do that, run the command below:

> composer install --no-dev

```
Open the specified entry point in your hosts file in your browser or make an entry in hosts file if not done.
```

##### On local:

```
php artisan route:clear
php artisan serve
```


**How to log in as admin:**

> _http(s)://example.com/admin/login_

```
email:admin@example.com
password:admin123
```
### Krayin CRM Multi Tenant SaaS

[Krayin CRM Multi Tenant SaaS](https://krayincrm.com/extensions/krayin-crm-multi-tenant-saas-extension/) Krayin Multitenant SaaS is a Laravel-based CRM solution that allows multiple businesses (tenants) to use a single application instance while keeping their data isolated and secure.

![enter image description here](https://raw.githubusercontent.com/krayin/temp-media/master/krayin-saas.png)

### WhatsApp CRM Integration

[Krayin CRM WhatsApp](https://krayincrm.com/extensions/krayin-crm-whatsapp-extension/) Extension enables the store administrator to generate leads via their WhatsApp number.

![enter image description here](https://raw.githubusercontent.com/krayin/temp-media/master/krayin-crm-whatsapp-integration.png)

### VoIP CRM Integration

[Krayin CRM VoIP](https://krayincrm.com/extensions/krayin-crm-voip/) extension allows the user to make Trunk calls over a broadband Internet connection and the user can also perform Inbound routes.

![enter image description here](https://raw.githubusercontent.com/krayin/temp-media/master/krayin-voip.png)

### License

AlamiaConnect CRM is licensed under a proprietary EULA. See `LICENSE` file for details.
Krayin CRM components are licensed under the MIT License. See `NOTICE.third-party.txt` for details.

### Attribution

This project is a fork of [Krayin CRM](https://github.com/krayin/laravel-crm). We thank the Webkul team for their excellent work.
See [docs/ATTRIBUTION.md](docs/ATTRIBUTION.md) for full details.
