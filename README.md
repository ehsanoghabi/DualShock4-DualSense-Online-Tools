# DualShock Calibration GUI

[![Persian](https://img.shields.io/badge/زبان-فارسی-blue.svg)](#نسخه-فارسی)

A web-based calibration tool for PlayStation DualShock 4, DualSense, and DualSense Edge controllers using the WebHID API.

The live version of this project is available at https://amoodigi.ir/online-tools/.

No installation is required: simply open the website in a WebHID-compatible browser.

## Features

- Controller connection via WebHID API
- Stick calibration and range calibration
- Input testing and visualization
- Battery status display
- Multi-language support (20+ languages)
- Progressive Web App (PWA) capabilities

## Docker

A pre-built Docker image is available for running DualShock Tools without installing any dependencies.

See the [Docker guide](DOCKER.md) for installation and usage instructions.

## Contributing

Interested in contributing? Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on submitting changes and pull requests.

## Development

### Prerequisites

- Node.js v20 or higher (v26 recommended — see `.nvmrc`). Older versions (14, 16, 18) will fail the build; the toolchain requires Node 20+.
- npm or yarn
- Modern browser with WebHID support (Chrome/Edge)

If you use [nvm](https://github.com/nvm-sh/nvm), run `nvm install && nvm use` in the project root to pick up the version from `.nvmrc`.

### Getting Started

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Build the application:**
   ```bash
   npm run build
   ```

3. **Start the development server:**
   ```bash
   npm run start
   ```
   The app will be available at `http://localhost:8080`. WebHID works here because `localhost` is treated as a secure context.

### Docker

Alternatively, build and run without installing Node:

```bash
docker compose up --build
```
The app is then available at `http://localhost:8080`.

### Development Scripts

- `npm run build` - Build the application for development
- `npm run build:prod` - Build the application for production
- `npm run clean` - Clean the dist directory
- `npm run serve` - Serve the built app over HTTP at `http://localhost:8080` (WebHID works on localhost)
- `npm run start` - Build and serve the app
- `npm run dev:full` - Build, watch for changes, and serve with auto-reload
- `npm run watch` - Watch for file changes and rebuild

### Development Workflow

For active development with auto-rebuild:
```bash
npm run dev:full
```
This will:
1. Build the application
2. Start watching for file changes
3. Serve the app at `http://localhost:8080`
4. Automatically rebuild when files change

### Important Notes

- **WebHID & secure contexts**: WebHID requires a secure context. `localhost` counts as secure, so the HTTP dev server (`http://localhost:8080`) works for local development. Reaching the app from another device would need HTTPS — use the production site for that.
- **Controller Support**: Only works in browsers with WebHID support (Chrome, Edge, Opera).

### Project Structure

- `js/` - Source JavaScript files
- `scss/` - Source SCSS files
- `templates/` - HTML template files
- `lang/` - Translation files
- `assets/` - SVG assets
- `dist/` - Built application (generated)

### Build System

The project uses Gulp for building:
- JavaScript bundling with Rollup
- SCSS concatenation and minification
- HTML processing and minification
- Asset optimization
- Development vs production builds

---
---

<a name="نسخه-فارسی"></a>
# رابط کاربری کالیبراسیون DualShock (DualShock Calibration GUI)

[![English](https://img.shields.io/badge/Language-English-blue.svg)](#dualshock-calibration-gui)

یک ابزار کالیبراسیون تحت وب برای کنترلرهای PlayStation DualShock 4، DualSense و DualSense Edge با استفاده از WebHID API.

نسخه آنلاین این پروژه در آدرس https://amoodigi.ir/online-tools/ در دسترس است.

این برنامه نیازی به نصب ندارد: فقط کافیست وب‌سایت را در مرورگری که از WebHID پشتیبانی می‌کند باز کنید.

## ویژگی‌ها

- اتصال کنترلر از طریق WebHID API
- کالیبراسیون استیک (آنالوگ) و دامنه حرکت
- تست و مصورسازی ورودی‌ها
- نمایش وضعیت باتری
- پشتیبانی از چند زبان (بیش از ۲۰ زبان)
- قابلیت‌های برنامه وب پیشرونده (PWA)

## داکر (Docker)

یک ایمیج داکر از پیش‌ساخته‌شده برای اجرای ابزارها بدون نیاز به نصب پیش‌نیازها در دسترس است.

برای مشاهده دستورالعمل‌های نصب و استفاده، [راهنمای داکر](DOCKER.md) را مطالعه کنید.

## مشارکت در پروژه

علاقه‌مند به مشارکت هستید؟ لطفاً برای اطلاع از قوانین ارسال تغییرات و پول ریکوئست‌ها (Pull Requests)، فایل [CONTRIBUTING.md](CONTRIBUTING.md) را مطالعه کنید.

## توسعه

### پیش‌نیازها

- Node.js نسخه 20 یا بالاتر (نسخه 26 توصیه می‌شود — به فایل `.nvmrc` مراجعه کنید). نسخه‌های قدیمی‌تر (14، 16، 18) در هنگام بیلد با خطا مواجه می‌شوند؛ این زنجیره ابزار به Node 20+ نیاز دارد.
- npm یا yarn
- یک مرورگر مدرن با پشتیبانی از WebHID (مانند Chrome یا Edge)

اگر از [nvm](https://github.com/nvm-sh/nvm) استفاده می‌کنید، دستور `nvm install && nvm use` را در مسیر اصلی پروژه اجرا کنید تا نسخه مشخص‌شده در `.nvmrc` فعال شود.

### شروع کار

۱. **نصب وابستگی‌ها:**
   ```bash
   npm install
   ```

۲. **بیلد کردن برنامه:**
   ```bash
   npm run build
   ```

۳. **راه‌اندازی سرور توسعه:**
   ```bash
   npm run start
   ```
   برنامه در آدرس `http://localhost:8080` در دسترس خواهد بود. WebHID در اینجا کار می‌کند زیرا `localhost` به عنوان یک بستر امن (secure context) شناخته می‌شود.

### استفاده از داکر

به عنوان یک راه جایگزین، می‌توانید برنامه را بدون نصب Node بیلد و اجرا کنید:

```bash
docker compose up --build
```
سپس برنامه در آدرس `http://localhost:8080` در دسترس خواهد بود.

### اسکریپت‌های توسعه

- `npm run build` - بیلد برنامه برای حالت توسعه
- `npm run build:prod` - بیلد برنامه برای حالت پروداکشن (نهایی)
- `npm run clean` - پاک کردن پوشه dist
- `npm run serve` - اجرای برنامه بیلدشده روی `http://localhost:8080` (WebHID روی لوکال‌هاست کار می‌کند)
- `npm run start` - بیلد و اجرای برنامه
- `npm run dev:full` - بیلد، بررسی تغییرات (watch) و اجرای برنامه با قابلیت بارگذاری مجدد خودکار
- `npm run watch` - بررسی تغییرات فایل‌ها و بیلد مجدد

### جریان کاری توسعه (Development Workflow)

برای توسعه فعال با قابلیت بیلد مجدد خودکار:
```bash
npm run dev:full
```
این دستور:
۱. برنامه را بیلد می‌کند.
۲. تغییرات فایل‌ها را زیر نظر می‌گیرد.
۳. برنامه را در آدرس `http://localhost:8080` اجرا می‌کند.
۴. با هر تغییری در فایل‌ها، برنامه را به صورت خودکار بازسازی (rebuild) می‌کند.

### نکات مهم

- **WebHID و بسترهای امن:** API مربوط به WebHID نیازمند یک بستر امن (HTTPS) است. `localhost` امن محسوب می‌شود، بنابراین سرور توسعه HTTP (`http://localhost:8080`) برای توسعه محلی کار می‌کند. دسترسی به برنامه از طریق دستگاهی دیگر نیازمند HTTPS است — برای این منظور از سایت پروداکشن استفاده کنید.
- **پشتیبانی از کنترلر:** این ابزار تنها در مرورگرهایی که از WebHID پشتیبانی می‌کنند (مانند کروم، اج، اپرا) کار می‌کند.

### ساختار پروژه

- `js/` - فایل‌های منبع جاوا اسکریپت
- `scss/` - فایل‌های منبع SCSS
- `templates/` - فایل‌های قالب HTML
- `lang/` - فایل‌های ترجمه زبان‌ها
- `assets/` - فایل‌های گرافیکی SVG
- `dist/` - فایل‌های بیلدشده نهایی برنامه (تولید خودکار)

### سیستم بیلد

این پروژه از Gulp برای فرآیند بیلد استفاده می‌کند:
- باندل کردن جاوا اسکریپت با Rollup
- ادغام و فشرده‌سازی SCSS
- پردازش و فشرده‌سازی HTML
- بهینه‌سازی فایل‌های گرافیکی (Assets)
- مدیریت بیلد برای محیط‌های توسعه و پروداکشن