احراز هویت
=====

دریافت توکن
------------

برای دریافت طرح های مربوط به تجهیزات الکترونیک از این وبسرویس استفاده کنید:

    ``POST``
    ``https://api-asato.mihaninsurance.com/api-manager/login``

.. code-block:: console

   curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/api-manager/login' \
      -H 'accept: application/json' \
      -H 'Content-Type: application/json''

بدنه ورودی :

.. code-block:: console

    {
      "username": <نام کاربری دریافتی شما>,
      "password": "<رمز عبور دریافتی شما>
    }

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": {
        "token": <api-token>
      }
    }


نحوه استفاده
----------------

برای استفاده از وبسرویس ها باید توکن دریافت خود را در هدر درخواست های خود به شکل زیر ارسال کنید :

.. code-block:: console

    Authorization: Bearer <api-token>
