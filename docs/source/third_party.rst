شخص ثالث
========

طرح‌ها
------

برای دریافت طرح‌ها از این وب‌سرویس استفاده کنید:

- **Method:** ``GET``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=5``

مثال درخواست:

.. code-block:: console

   curl -X 'GET' \
     'https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=5&page=1&size=1' \
     -H 'accept: application/json'

پارامترهای ورودی
~~~~~~~~~~~~~~~~

- ``page``
- ``size``

خروجی وب‌سرویس
~~~~~~~~~~~~~~

.. code-block:: json

    {
      "status": "ok",
      "data": [
        {
          "id": "5cb0bbb4-bb7b-42e8-9383-03dd572edf38",
          "code": 1,
          "created_at": "2025-04-07T10:43:11.508768Z",
          "updated_at": "2025-04-07T10:51:16.626477Z",
          "insurance_type_code": 5,
          "festival_code": null,
          "payload": {
            "code": 1,
            "contract_code": 4514,
            "life_cov": 21333333000,
            "driver_accidents_cov": 16000000000
          },
          "insurance_type": {
            "id": "35ff6ab2-b24b-4559-b36d-4780dc101a55",
            "code": 5,
            "created_at": "2024-06-15T09:33:06.717500Z",
            "updated_at": null,
            "title": "اتومبيل - شخص ثالث",
            "name": "اتومبيل ثالث",
            "icon": "nan",
            "is_active": true,
            "type": "PROPERTY",
            "is_buy_active": null
          },
          "festival": null
        }
      ],
      "page": 1,
      "size": 10,
      "count": 1
    }

بیمه‌نامه قبلی
--------------

برای دریافت بیمه‌نامه قبلی شخص از این دو وب‌سرویس استفاده کنید.

دریافت بر اساس کد ملی
~~~~~~~~~~~~~~~~~~~~~

- **Method:** ``POST``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/inquiry/car/get_unique_policy_by_national_id``

.. code-block:: console

   curl -X 'POST' \
     'https://api-asato.mihaninsurance.com/inquiry/car/get_unique_policy_by_national_id' \
     -H 'accept: application/json' \
     -H 'Authorization: Bearer <توکن شما که در مرحله احراز هویت گرفتید>' \
     -H 'Content-Type: application/json' \
     -d '{
       "national_id": "<nid>"
     }'

بدنه ورودی:

.. code-block:: json

    {
      "national_id": "**"
    }

دریافت بر اساس شماره بیمه‌نامه
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- **Method:** ``POST``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/inquiry/car/get_policy_by_policy_code``

.. code-block:: console

   curl -X 'POST' \
     'https://api-asato.mihaninsurance.com/inquiry/car/get_policy_by_policy_code' \
     -H 'accept: application/json' \
     -H 'Authorization: Bearer <توکن شما که در مرحله احراز هویت گرفتید>' \
     -H 'Content-Type: application/json' \
     -d '{
       "policy_code": "<policy_code>"
     }'

بدنه ورودی:

.. code-block:: json

    {
      "policy_code": "**"
    }

خروجی وب‌سرویس‌ها
~~~~~~~~~~~~~~~~~

.. code-block:: json

    {
      "status": "ok",
      "data": [
        {
          "car_grp_cod": "2",
          "cmp_cod": "2",
          "cmp_nam": "**",
          "cntry_cod": null,
          "dis_fn_yr_num": "1",
          "dis_fn_yr_prcnt": "5",
          "dis_lf_yr_num": "1",
          "dis_lf_yr_prcnt": "5",
          "dis_prsn_yr_num": "1",
          "dis_prsn_yr_prcnt": "5",
          "disc_bdn_yr_num": null,
          "fnd_cst": "0.00",
          "h_bgn_dte": "1404/06/12",
          "h_end_dte": "1405/06/11",
          "h_isu_dte": "1404/06/11",
          "ins_nam": "**",
          "last_cmp_cod": "18",
          "last_cmp_doc_no": null,
          "losses": null,
          "mtr_num": "**",
          "ntnl_id": "**",
          "plcy_unq_cod": "**",
          "plk": "**",
          "prd_dte": "1398",
          "prnt_cmp_doc_no": "**",
          "shs_num": "**",
          "typ_plcy": "بيمه ثالث و حوادث",
          "usg_cod": "8",
          "usg_nam": "شخصی",
          "vin": "**",
          "veh_nam": "**",
          "veh_sys_cod": "2"
        }
      ],
      "page": null,
      "size": null,
      "count": null
    }

ساخت درخواست صدور بیمه‌نامه
----------------------------

ایجاد فاکتور صدور
~~~~~~~~~~~~~~~~~

- **Method:** ``POST``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party``

بروزرسانی فاکتور صدور
~~~~~~~~~~~~~~~~~~~~~

- **Method:** ``PATCH``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/<آیدی صدور بیمه نامه>``

بدنه ورودی
~~~~~~~~~~

.. code-block:: json

    {
      "insurance_plan_code": "<کد طرح انتخابی که در مرحله قبل گرفتید>",
      ...
      "vehicle_plaque_kind_code": "<کد نوع پلاک خودرو>"
    }

ثبت درخواست در فناوران
----------------------

- **Method:** ``POST``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/submit/<آیدی صدور بیمه نامه>``

استعلام قیمت درخواست
---------------------

- **Method:** ``POST``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/check_price/<آیدی صدور بیمه نامه>``

پرداخت فاکتور
-------------

- **Method:** ``POST``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/insurance_policy_buy/factor/pay``

دریافت فایل PDF بیمه‌نامه شخص ثالث
==================================

درخواست
--------

- **Method:** ``GET``
- **URL:**  
  ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/print_by_code/{policy_code}/``

پارامتر مسیر
~~~~~~~~~~~~

- ``policy_code`` (اجباری)

هدرهای درخواست
~~~~~~~~~~~~~~

.. code-block:: http

    accept: application/json
    Authorization: Bearer {token}

مثال
~~~~~

.. code-block:: bash

    curl -X 'GET' \
      'https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/print_by_code/12345ABC/' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer your_access_token_here' \
      --output policy.pdf
