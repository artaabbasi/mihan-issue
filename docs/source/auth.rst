احراز هویت
==========

دریافت توکن
-----------

برای دریافت توکن احراز هویت و استفاده از وب‌سرویس‌های مربوط به تجهیزات الکترونیک، از وب‌سرویس زیر استفاده کنید:

``POST``
``https://api-asato.mihaninsurance.com/api-manager/login``

نمونه درخواست:

.. code-block:: console

   curl -X POST \
     'https://api-asato.mihaninsurance.com/api-manager/login' \
     -H 'accept: application/json' \
     -H 'Content-Type: application/json'

بدنه ورودی:

.. code-block:: console

   {
     "username": "<نام کاربری دریافتی شما>",
     "password": "<رمز عبور دریافتی شما>"
   }

خروجی وب‌سرویس:

.. code-block:: console

   {
     "status": "ok",
     "data": {
       "token": "<api-token>"
     }
   }


نحوه استفاده
------------

برای استفاده از وب‌سرویس‌ها، لازم است توکن دریافتی را در هدر درخواست‌های خود به شکل زیر ارسال کنید:

.. code-block:: console

   Authorization: Bearer <api-token>
