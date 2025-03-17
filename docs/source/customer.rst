بیمه گزار
=====

برای دریافت کد بیمه گزار در سیستم بیمه مرکزی باید ابتدا وجود کاربر را توسط وبسرویس استعلام
چک کنید و سپس در صورت عدم وجود کاربر یک کاربری برای بیمه گزار خود بسازید


استعلام بیمه گزار
=====

با فراخوانی این وب سرویس وجود کاربر در سیستم بیمه استعلام میشود :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insureds/check_customers``


.. code-block:: console

   curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/insureds/check_customers' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer  <توکن شما که در مرحله احراز هویت گرفتید> \
      -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "customers": [
        {
          "role_id": 161, # برای گرفتن کد بیمه گزار 161 ارسال شود
          "national_code": <کد ملی کاربر>
        }
      ]
    }

بدنه خروجی :

.. code-block:: console

    {
      "status": "ok",
      "data": {
        "customers": [
          {
            "role_id": 161,
            "customer_id": ...
          }
        ]
      }
    }

در صورت مقدار داشتن فیلد``customer_id`` در خروجی این کد بیمه گزار است و در صورت مقدار نداشتن آن باید در مرحله بعدی برای کاربر یک کد بیمه بسازید

ساخت بیمه گزار
=====

با فراخوانی این وب سرویس کاربر در سیستم بیمه ساخته میشود :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insureds/create_customers``


.. code-block:: console

   curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/insureds/create_customers' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer  <توکن شما که در مرحله احراز هویت گرفتید> \
      -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "role_id": 161,
      "national_code": <کد ملی کاربر>,
      "city_id": <کد شهر کاربر>,
      "home_phone": "string",
      "address": "string",
      "birth_date": "0481/06/20",
      "mobile": "string",
      "tel": "string"
    }

بدنه خروجی :

.. code-block:: console

    {
      "status": "ok",
      "data": {
        "code": 1111111,
        ...
    }

``code`` در خروجی وبسرویس مقدار کد بیمه گزار را دارد