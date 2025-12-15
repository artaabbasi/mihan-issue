سرویس پکیج بیمه‌نامه‌های مسافرتی
=====

ساخت و به روزرسانی و دریافت
------------

این سرویس برای **ثبت اولیه پکیج بیمه‌نامه‌های مسافرتی** استفاده می‌شود. پس از ثبت اولیه، سیستم به‌صورت **Background Task** فرآیند صدور آنلاین هر یک از بیمه‌نامه‌های مسافرتی موجود در پکیج را آغاز می‌کند.

نکته مهم:

```
- این سرویس صرفاً ثبت اولیه پکیج را انجام می‌دهد.
- فرآیند صدور بیمه‌نامه‌ها به‌صورت غیرهمزمان (Asynchronous) انجام می‌شود.
- **در صورتی که حداقل یکی از بیمه‌نامه‌ها صادر شود، امکان حذف پکیج وجود نخواهد داشت.**
```


ایجاد پکیج بیمه‌نامه مسافرتی
----------------------------

برای ایجاد یک پکیج جدید بیمه‌نامه مسافرتی از این وب‌سرویس استفاده کنید:

``POST``
``/policy-package/traveling-insurance-package``

نمونه درخواست:

.. code-block:: bash

    curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/policy-package/traveling-insurance-package' \
      -H 'accept: application/json' \
      -H 'Content-Type: application/json' \
      -d '{
        "begin_date": "2025-06-01",
        "end_date": "2025-06-30",
        "province_code": 23,
        "city_code": 2301,
        "customer_code": 10001,
        "insurance_item_description": "بیمه مسافرتی شنگن",
        "address": "تهران، خیابان ...",
        "usage_description": "سفر توریستی",
        "insured_count": 2,
        "insured_customer_code": 20001,
        "insured_national_code": "0012345678",
        "insured_phone_number": "09120000000",
        "insured_full_name": "علی رضایی"
      }'

بدنه ورودی


* `begin_date`
  تاریخ شروع اعتبار بیمه‌نامه‌های مسافرتی در پکیج.

* `end_date`
  تاریخ پایان اعتبار بیمه‌نامه‌های مسافرتی در پکیج.

* `province_code`
  کد استان محل اقامت یا ثبت درخواست بیمه‌گذار.

* `city_code`
  کد شهر مرتبط با بیمه‌گذار یا محل صدور بیمه‌نامه.

* `customer_code`
  کد مشتری (بیمه‌گذار) در سیستم.

* `insurance_item_description`
  توضیح مختصر درباره نوع بیمه مسافرتی (مثلاً شنگن، زیارتی، توریستی).

* `address`
  آدرس کامل بیمه‌گذار.

* `usage_description`
  توضیح درباره هدف یا نوع استفاده از بیمه‌نامه (مانند سفر تفریحی، کاری یا زیارتی).

* `insured_count`
  تعداد افراد بیمه‌شده در این پکیج.

* `insured_customer_code`
  کد مشتری فرد بیمه‌شده (در صورت تفاوت با بیمه‌گذار).

* `insured_national_code`
  کد ملی فرد بیمه‌شده.

* `insured_phone_number`
  شماره تماس فرد بیمه‌شده.

* `insured_full_name`
  نام و نام خانوادگی کامل فرد بیمه‌شده.

پاسخ وب‌سرویس



در صورت موفقیت، اطلاعات پکیج ایجادشده به همراه شناسه یکتا بازگردانده می‌شود:

.. code-block:: json

    {
      "status": "ok",
      "data": {
        "id": "string",
        "user_id": "string",
        "begin_date": "string",
        "end_date": "string",
        "province_code": 0,
        "city_code": 0,
        "customer_code": 0,
        "insurance_item_description": "string",
        "address": "string",
        "usage_description": "string",
        "insured_count": 0,
        "insured_customer_code": 0,
        "insured_national_code": "string",
        "insured_phone_number": "string",
        "insured_full_name": "string",
        "created_at": "2025-12-15T14:25:54.334Z",
        "updated_at": "2025-12-15T14:25:54.334Z"
      }
    }

توضیح فیلدهای پاسخ

* `id`
  شناسه یکتای پکیج بیمه‌نامه مسافرتی که در ادامه فرآیند استفاده می‌شود.

* `user_id`
  شناسه کاربری که درخواست ایجاد پکیج را ثبت کرده است.

* `created_at`
  تاریخ و زمان ایجاد پکیج در سیستم.

* `updated_at`
  تاریخ و زمان آخرین به‌روزرسانی پکیج.



## دریافت جزئیات پکیج بیمه‌نامه مسافرتی

برای دریافت اطلاعات کامل یک پکیج ثبت‌شده:

`GET`
`https://api-asato.mihaninsurance.com/policy-package/traveling-insurance-package/{traveling_insurance_package_id}`

توضیح:

```این وب‌سرویس اطلاعات کامل پکیج، وضعیت صدور بیمه‌نامه‌ها و جزئیات افراد بیمه‌شده را بازمی‌گرداند.
```

به‌روزرسانی پکیج بیمه‌نامه مسافرتی
----------------------------------

برای ویرایش اطلاعات پکیج (در صورتی که هنوز هیچ بیمه‌نامه‌ای صادر نشده باشد):

``PATCH``
``https://api-asato.mihaninsurance.com/policy-package/traveling-insurance-package/{traveling_insurance_package_id}``

توضیح:
```
* تنها پکیج‌هایی قابل ویرایش هستند که فرآیند صدور آن‌ها نهایی نشده باشد.
* پس از شروع صدور یا صدور حداقل یک بیمه‌نامه، امکان ویرایش وجود ندارد.
```

## حذف پکیج بیمه‌نامه مسافرتی

برای حذف یک پکیج ثبت‌شده:

`DELETE`
`https://api-asato.mihaninsurance.com/policy-package/traveling-insurance-package/{traveling_insurance_package_id}`

قوانین حذف

```
- در صورتی که **هیچ بیمه‌نامه‌ای صادر نشده باشد**، حذف پکیج امکان‌پذیر است.
- اگر حداقل یک بیمه‌نامه در پکیج صادر شده باشد، عملیات حذف با خطا مواجه خواهد شد.
```


