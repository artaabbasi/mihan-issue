بیمه گزار
=====

برای دریافت کد بیمه گزار در سیستم بیمه مرکزی باید ابتدا وجود کاربر را توسط وبسرویس استعلام
چک کنید و سپس در صورت عدم وجود کاربر یک کاربری برای بیمه گزار خود بسازید


استعلام بیمه گزار
----------------

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
          "national_code": XXXXXX
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

در صورت مقدار داشتن فیلد
``customer_id``
در خروجی این کد بیمه گزار است و در صورت مقدار نداشتن آن باید در مرحله بعدی برای کاربر یک کد بیمه بسازید


ساخت بیمه گزار
----------------

با فراخوانی این وب سرویس کاربر در سیستم بیمه ساخته میشود :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insureds/create_customer``


.. code-block:: console

   curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/insureds/create_customer' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer  <توکن شما که در مرحله احراز هویت گرفتید> \
      -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "role_id": 161,
      "role_ids":[161,162],//درصورت نیاز به ساختن چند رول همزمان
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
        "id": "1a3dc9c2-46fe-4cf6-8b4a-a98995b65b39",
        "code": XXXXX,
        "created_at": "2024-08-06T08:32:28.198179Z",
        "updated_at": "2025-03-17T08:12:41.963870Z",
        "ad_birth_day": 10,
        "ad_birth_month": 5,
        "ad_birth_year": 2003,
        "address": XXXXX,
        "birth_city_code": null,
        "birth_day": 20,
        "birth_month": 2,
        "birth_year": 1382,
        "cii_mobile_status": 2128,
        "cii_validation_status": 2128,
        "city_code": 1104,
        "company_code": "None",
        "economic_code": "None",
        "education_field": "None",
        "education_level_code": null,
        "email": null,
        "en_address": null,
        "en_last_name": null,
        "en_name": null,
        "father_name": "فرزاد",
        "fax": null,
        "gender_code": 26,
        "identity_no": "0",
        "identity_no_issu_place": null,
        "is_iranian": 1,
        "is_main_person": 1,
        "is_valid": 1,
        "is_verified": 1,
        "job_address": null,
        "last_name": "عباسي زنجاني",
        "legal_person_registration_date": null,
        "legal_person_registry_office_status": null,
        "main_person_code": null,
        "marital_status": "None",
        "mobile": XXXXX,
        "name": "آرتا",
        "national_code": XXXXXX,
        "nationality_code": null,
        "naturalized_code": null,
        "ownership_code": 56,
        "passport_no": "None",
        "person_kind_code": 46,
        "postal_code": XXXXXX,
        "register_no": "None",
        "religion_code": null,
        "tel": XXXXXX,
        "city": null,
        "roles": [
          161,
          162
        ]
      }
    }

``code`` در خروجی وبسرویس مقدار کد بیمه گزار را دارد


آپدیت بیمه گزار
----------------

با فراخوانی این وب سرویس کاربر در سیستم بیمه آپدیت میشود :

    ``PATCH``
    ``https://api-asato.mihaninsurance.com/insureds/update_customer``


.. code-block:: console

   curl -X 'PATCH' \
      'https://api-asato.mihaninsurance.com/insureds/update_customer/{customer_id}' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer  <توکن شما که در مرحله احراز هویت گرفتید> \
      -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "role_id": 161,
      "city_id": XXXXX,
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
        "id": "1a3dc9c2-46fe-4cf6-8b4a-a98995b65b39",
        "code": XXXXX,
        "created_at": "2024-08-06T08:32:28.198179Z",
        "updated_at": "2025-03-17T08:12:41.963870Z",
        "ad_birth_day": 10,
        "ad_birth_month": 5,
        "ad_birth_year": 2003,
        "address": XXXXX,
        "birth_city_code": null,
        "birth_day": 20,
        "birth_month": 2,
        "birth_year": 1382,
        "cii_mobile_status": 2128,
        "cii_validation_status": 2128,
        "city_code": 1104,
        "company_code": "None",
        "economic_code": "None",
        "education_field": "None",
        "education_level_code": null,
        "email": null,
        "en_address": null,
        "en_last_name": null,
        "en_name": null,
        "father_name": "فرزاد",
        "fax": null,
        "gender_code": 26,
        "identity_no": "0",
        "identity_no_issu_place": null,
        "is_iranian": 1,
        "is_main_person": 1,
        "is_valid": 1,
        "is_verified": 1,
        "job_address": null,
        "last_name": "عباسي زنجاني",
        "legal_person_registration_date": null,
        "legal_person_registry_office_status": null,
        "main_person_code": null,
        "marital_status": "None",
        "mobile": XXXXX,
        "name": "آرتا",
        "national_code": XXXXXX,
        "nationality_code": null,
        "naturalized_code": null,
        "ownership_code": 56,
        "passport_no": "None",
        "person_kind_code": 46,
        "postal_code": XXXXXX,
        "register_no": "None",
        "religion_code": null,
        "tel": XXXXXX,
        "city": null,
        "roles": [
          161,
          162
        ]
      }
    }

دریافت بیمه گزار
----------------

با فراخوانی این وب سرویس اطلاعات کاربر در سیستم بیمه برگردانده میشود و میتوان کاربر را با دو روش کد ملی و کد رایانه بیمه دریافت کرد  :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insureds/get_customer``


.. code-block:: console

   curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/insureds/get_customer?national_code=XXXXX' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer  <توکن شما که در مرحله احراز هویت گرفتید> \
      -H 'Content-Type: application/json'


: پارامتر های ورودی

    ``national_code`` یا ``customer_code``


بدنه خروجی :

.. code-block:: console

    {
      "status": "ok",
      "data": {
        "id": "1a3dc9c2-46fe-4cf6-8b4a-a98995b65b39",
        "code": XXXXX,
        "created_at": "2024-08-06T08:32:28.198179Z",
        "updated_at": "2025-03-17T08:12:41.963870Z",
        "ad_birth_day": 10,
        "ad_birth_month": 5,
        "ad_birth_year": 2003,
        "address": XXXXX,
        "birth_city_code": null,
        "birth_day": 20,
        "birth_month": 2,
        "birth_year": 1382,
        "cii_mobile_status": 2128,
        "cii_validation_status": 2128,
        "city_code": 1104,
        "company_code": "None",
        "economic_code": "None",
        "education_field": "None",
        "education_level_code": null,
        "email": null,
        "en_address": null,
        "en_last_name": null,
        "en_name": null,
        "father_name": "فرزاد",
        "fax": null,
        "gender_code": 26,
        "identity_no": "0",
        "identity_no_issu_place": null,
        "is_iranian": 1,
        "is_main_person": 1,
        "is_valid": 1,
        "is_verified": 1,
        "job_address": null,
        "last_name": "عباسي زنجاني",
        "legal_person_registration_date": null,
        "legal_person_registry_office_status": null,
        "main_person_code": null,
        "marital_status": "None",
        "mobile": XXXXX,
        "name": "آرتا",
        "national_code": XXXXXX,
        "nationality_code": null,
        "naturalized_code": null,
        "ownership_code": 56,
        "passport_no": "None",
        "person_kind_code": 46,
        "postal_code": XXXXXX,
        "register_no": "None",
        "religion_code": null,
        "tel": XXXXXX,
        "city": null,
        "roles": [
          161,
          162
        ]
      }
    }


ساخت سایر نقش ها برای مشتری
----------------

با فراخوانی این وب سرویس نقش ها مورد نیاز کاربر در سیستم بیمه ساخته میشود : (در حالتی که کاربر قبلا کد بیمه گزاری دارد ولی نقش جدید برای وی نیاز است که ساخته شود)

    ``POST``
    ``https://api-asato.mihaninsurance.com/insureds/clone_customer``


.. code-block:: console

   curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/insureds/clone_customer' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer  <توکن شما که در مرحله احراز هویت گرفتید> \
      -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "customer_code": XXXXX,
      "roles": [
        161, 162
      ]
    }

بدنه خروجی :

.. code-block:: console

    {
      "status": "ok",
      "data": {
        "id": "1a3dc9c2-46fe-4cf6-8b4a-a98995b65b39",
        "code": XXXXX,
        "created_at": "2024-08-06T08:32:28.198179Z",
        "updated_at": "2025-03-17T08:12:41.963870Z",
        "ad_birth_day": 10,
        "ad_birth_month": 5,
        "ad_birth_year": 2003,
        "address": XXXXX,
        "birth_city_code": null,
        "birth_day": 20,
        "birth_month": 2,
        "birth_year": 1382,
        "cii_mobile_status": 2128,
        "cii_validation_status": 2128,
        "city_code": 1104,
        "company_code": "None",
        "economic_code": "None",
        "education_field": "None",
        "education_level_code": null,
        "email": null,
        "en_address": null,
        "en_last_name": null,
        "en_name": null,
        "father_name": "فرزاد",
        "fax": null,
        "gender_code": 26,
        "identity_no": "0",
        "identity_no_issu_place": null,
        "is_iranian": 1,
        "is_main_person": 1,
        "is_valid": 1,
        "is_verified": 1,
        "job_address": null,
        "last_name": "عباسي زنجاني",
        "legal_person_registration_date": null,
        "legal_person_registry_office_status": null,
        "main_person_code": null,
        "marital_status": "None",
        "mobile": XXXXX,
        "name": "آرتا",
        "national_code": XXXXXX,
        "nationality_code": null,
        "naturalized_code": null,
        "ownership_code": 56,
        "passport_no": "None",
        "person_kind_code": 46,
        "postal_code": XXXXXX,
        "register_no": "None",
        "religion_code": null,
        "tel": XXXXXX,
        "city": null,
        "roles": [
          161,
          162
        ]
      }
    }


لیست کد های نقش های کاربران
----------------

| ``161`` : ``بیمه گزار``
| ``162`` : ``بیمه شده``
| ``166`` : ``(مالک و زیان دیده و ...) سایر اشخاص``

