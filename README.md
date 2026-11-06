# AGY Adaptor

An experimental API-compatibility layer exploring how an OpenAI-style interface can work with a command-line model runtime.

> **Status:** Discontinued proof of concept. This showcase contains documentation only; it is not a production service or a supported integration.

## Overview

The project explored translating structured client requests into a downstream model workflow and returning responses in familiar JSON and server-sent event (SSE) formats. Its main engineering focus was the boundary between the client-facing API and the runtime: request normalization, streaming behavior, tool-call representation, concurrency, timeouts, and process cleanup.

## Engineering scope

- Normalize chat-style and response-style request payloads.
- Handle JSON responses and streaming output, including incremental content.
- Explore mapping structured tool calls to a prompt-oriented runtime.
- Manage request timeouts, concurrency, child-process lifecycle, and cleanup.
- Provide health checks and repeatable validation with automated tests.

## Design takeaways

- **Compatibility is behavioral.** Matching endpoint shapes does not guarantee consistent handling of errors, streaming, or tool calls.
- **Streaming needs explicit contracts.** Partial output, completion signals, and failures during a stream need deliberate treatment.
- **Runtime lifecycle is part of reliability.** Cancellation, timeouts, and cleanup matter when work is delegated to subprocesses.
- **Tests and live validation answer different questions.** Controlled tests improve repeatability; they do not prove the availability or behavior of an external runtime.
- **Keep operational details separate.** Public project documentation should not expose environment-specific deployment information.

## Project status

This experiment is discontinued and unmaintained. The repository is a sanitized technical retrospective, not the original source repository. It does not include deployment configuration, credentials, or environment-specific infrastructure details.

---

# AGY Adaptor — فارسی

یک لایهٔ آزمایشی برای بررسی سازگاری میان رابطی شبیه OpenAI و محیط اجرای مدل مبتنی بر خط فرمان.

> **وضعیت:** نمونهٔ اثبات مفهوم متوقف‌شده. این مخزن فقط مستندات نمایشی دارد و سرویس تولیدی یا یکپارچه‌سازی پشتیبانی‌شده نیست.

## معرفی

این پروژه تبدیل درخواست‌های ساختاریافتهٔ کلاینت به یک جریان کاری مدل بالادستی و بازگرداندن پاسخ در قالب‌های آشنای JSON و رویدادهای جریانی SSE را بررسی می‌کرد. تمرکز فنی بر مرز میان API کلاینت و محیط اجرا بود: نرمال‌سازی درخواست، رفتار استریمینگ، نمایش فراخوانی ابزار، هم‌زمانی، timeout و پاک‌سازی فرایندها.

## حوزهٔ فنی

- نرمال‌سازی درخواست‌های مبتنی بر چت و قالب پاسخ.
- مدیریت پاسخ‌های JSON و خروجی جریانی، از جمله محتوای تدریجی.
- بررسی نگاشت فراخوانی ابزارهای ساختاریافته به محیط اجرایی مبتنی بر prompt.
- مدیریت مهلت درخواست، هم‌زمانی، چرخهٔ عمر فرایند فرزند و پاک‌سازی.
- ارائهٔ بررسی سلامت و اعتبارسنجی تکرارپذیر با آزمون‌های خودکار.

## آموخته‌های طراحی

- **سازگاری رفتاری مهم است.** مشابه‌بودن شکل endpointها، رفتار یکسان در خطاها، استریمینگ یا فراخوانی ابزار را تضمین نمی‌کند.
- **استریمینگ به قرارداد روشن نیاز دارد.** خروجی ناقص، علامت پایان و خطاهای حین جریان باید آگاهانه مدیریت شوند.
- **چرخهٔ عمر محیط اجرا بخشی از قابلیت اطمینان است.** لغو، timeout و پاک‌سازی در واگذاری کار به subprocess اهمیت دارند.
- **آزمون و اعتبارسنجی زنده به پرسش‌های متفاوت پاسخ می‌دهند.** آزمون کنترل‌شده تکرارپذیری را بهتر می‌کند، اما دسترس‌پذیری یا رفتار محیط اجرای بیرونی را اثبات نمی‌کند.
- **جزئیات عملیاتی باید جدا بمانند.** مستندات عمومی نباید اطلاعات وابسته به محیط استقرار را افشا کنند.

## وضعیت پروژه

این تجربه متوقف شده و نگهداری نمی‌شود. این مخزن یک مرور فنیِ پالایش‌شده است، نه مخزن کد اصلی؛ پیکربندی استقرار، اطلاعات دسترسی و جزئیات زیرساختی وابسته به محیط در آن قرار ندارند.
