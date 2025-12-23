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
      "insurer_customer_code": "<کد بیمه‌گزار>",
      "location_code": "<واحد صدور بیمه‌نامه>",
      "start_from_days": "<تعداد روزهای شروع از تاریخ صدور>",
      "national_code": "<کد ملی بیمه‌گزار>",
      "previous_policy_status": "<وضعیت بیمه‌نامه قبلی>",
      "previous_policy_ci_number": "<شماره بیمه‌نامه شخص ثالث قبلی>",
      "previous_policy_begin_date": "<تاریخ شروع بیمه‌نامه قبلی>",
      "previous_policy_end_date": "<تاریخ پایان بیمه‌نامه قبلی>",
      "previous_policy_no": "<شماره بیمه‌نامه قبلی>",
      "previous_policy_discount_duration": "<مدت زمان تخفیف بیمه‌نامه قبلی>",
      "previous_policy_discount_percent": "<درصد تخفیف بیمه‌نامه قبلی>",
      "has_dmg": "<آیا خسارت داشته است>",
      "life_dmg_count": "<تعداد خسارت‌های جانی>",
      "financial_dmg_count": "<تعداد خسارت‌های مالی>",
      "driver_accidents_dmg_count": "<تعداد خسارت‌های مرتبط با تصادف راننده>",
      "previous_policy_driver_accidents_discount_duration": "<مدت زمان تخفیف تصادف راننده در بیمه‌نامه قبلی>",
      "previous_policy_driver_accidents_discount_percent": "<درصد تخفیف تصادف راننده در بیمه‌نامه قبلی>",
      "accident_violations_count": "<تعداد تخلفات حادثه‌ای>",
      "form_seri": "<سری فرم بیمه‌نامه>",
      "form_serial": "<شماره سریال فرم بیمه‌نامه>",
      "transferor_policy_ci_number": "<شماره بیمه‌نامه شخص ثالث انتقال‌دهنده>",
      "transferor_policy_no": "<شماره بیمه‌نامه انتقال‌دهنده>",
      "transferor_policy_end_date": "<تاریخ پایان بیمه‌نامه انتقال‌دهنده>",
      "transferor_discount_duration": "<مدت زمان تخفیف انتقال‌دهنده>",
      "transferor_discount_percent": "<درصد تخفیف انتقال‌دهنده>",
      "driver_accidents_transfer_discount_duration": "<مدت زمان تخفیف تصادفات راننده انتقال‌دهنده>",
      "driver_accidents_transfer_discount_percent": "<درصد تخفیف تصادفات راننده انتقال‌دهنده>",
      "transferor_plaque_serial": "<شماره سریال پلاک انتقال‌دهنده>",
      "transferor_plaque_right_no": "<شماره سمت راست پلاک انتقال‌دهنده>",
      "transferor_plaque_left_no": "<شماره سمت چپ پلاک انتقال‌دهنده>",
      "economic_no": "<شماره اقتصادی بیمه‌گزار>",
      "label_serial_no": "<شماره سریال برچسب بیمه‌نامه>",
      "doc_package_key": "<کلید بسته مدارک بیمه‌نامه>",
      "transferor_plaque_no": "<شماره پلاک انتقال‌دهنده>",
      "plaque_owner_code": "<کد مالک پلاک خودرو>",
      "transferor_person_code": "<کد شخص انتقال‌دهنده>",
      "extended_policy_code": "<کد بیمه‌نامه تمدیدی>",
      "previous_insurance_corp_code": "<کد شرکت بیمه قبلی>",
      "agent_code": "<کد نمایندگی صدور بیمه‌نامه>",
      "is_in_free_region": "<آیا در منطقه آزاد است>",
      "free_region_code": "<کد منطقه آزاد>",
      "financial_cov": "<میزان پوشش مالی بیمه‌نامه>",
      "life_cov": "<میزان پوشش جانی بیمه‌نامه>",
      "driver_accidents_cov": "<میزان پوشش خسارت‌های راننده>",
      "has_transfer_discount": "<آیا تخفیف انتقال دارد>",
      "reason_for_has_not_previous_policy_code": "<دلیل نداشتن بیمه‌نامه قبلی>",
      "transferor_relation_type_code": "<کد نوع رابطه انتقال‌دهنده>",
      "transferor_insurance_corp_code": "<کد شرکت بیمه انتقال‌دهنده>",
      "transferor_policy_code": "<کد بیمه‌نامه انتقال‌دهنده>",
      "transferor_tariff_group_code": "<کد گروه تعرفه انتقال‌دهنده>",
      "transferor_plaque_sample_code": "<کد نمونه پلاک انتقال‌دهنده>",
      "transferor_plaque_middle_code_code": "<کد بخش میانی پلاک انتقال‌دهنده>",
      "marketer_code": "<کد بازاریاب بیمه‌نامه>",
      "policy_usage_type_code": "<کد نوع استفاده بیمه‌نامه>",
      "transferor_plaque_city_code": "<کد شهر پلاک انتقال‌دهنده>",
      "vehicle_code": "<کد خودرو>",
      "vehicle_plaque_serial": "<شماره سریال پلاک خودرو>",
      "vehicle_plaque_left_no": "<شماره سمت چپ پلاک خودرو>",
      "vehicle_plaque_right_no": "<شماره سمت راست پلاک خودرو>",
      "vehicle_plaque_date": "<تاریخ صدور پلاک خودرو>",
      "vehicle_no": "<شماره موتور خودرو>",
      "vehicle_chassis_no": "<شماره شاسی خودرو>",
      "vehicle_built_year": "<سال ساخت خودرو>",
      "vehicle_vin": "<شماره VIN خودرو>",
      "vehicle_plaque_no": "<شماره پلاک خودرو>",
      "vehicle_third_party_spare_count": "<تعداد بیمه‌های شخص ثالث یدک خودرو>",
      "vehicle_spare_desc": "<توضیحات یدک خودرو>",
      "vehicle_spare_plaque_no": "<شماره پلاک یدک خودرو>",
      "vehicle_spare_plaque_date": "<تاریخ صدور پلاک یدک خودرو>",
      "vehicle_spare_plaque_serial": "<شماره سریال پلاک یدک خودرو>",
      "vehicle_spare_plaque_right_no": "<شماره سمت راست پلاک یدک خودرو>",
      "vehicle_spare_plaque_left_no": "<شماره سمت چپ پلاک یدک خودرو>",
      "vehicle_spare_plaque_vin": "<شماره VIN پلاک یدک خودرو>",
      "vehicle_kind_code": "<کد نوع خودرو>",
      "vehicle_use_type_code": "<کد نوع استفاده خودرو>",
      "vehicle_plaque_sample_code": "<کد نمونه پلاک خودرو>",
      "vehicle_plaque_middle_code": "<کد بخش میانی پلاک خودرو>",
      "vehicle_color_code": "<کد رنگ خودرو>",
      "vehicle_fuel_type_code": "<کد نوع سوخت خودرو>",
      "vehicle_plaque_city_code": "<کد شهر پلاک خودرو>",
      "vehicle_has_third_party_spare": "<آیا خودرو بیمه شخص ثالث یدک دارد>",
      "vehicle_spare_plaque_sample_code": "<کد نمونه پلاک یدک خودرو>",
      "vehicle_spare_plaque_middle_code": "<کد بخش میانی پلاک یدک خودرو>",
      "vehicle_spare_plaque_city_code": "<کد شهر پلاک یدک خودرو>",
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

پرداخت فاکتور در فناوران
------------------------

با فراخوانی این وب‌سرویس، پرداخت فاکتور انجام شده و شناسه تراکنش بازگردانده می‌شود:

``POST``
``https://api-asato.mihaninsurance.com/insurance_policy_buy/factor/pay``

.. code-block:: console

   curl -X POST \
     'https://api-asato.mihaninsurance.com/insurance_policy_buy/factor/pay' \
     -H 'accept: application/json' \
     -H 'Content-Type: application/json'

بدنه ورودی:

.. code-block:: json

   {
     "factor_id": "083ba303-b9c6-412b-a8d7-e1b59f96df10",
     "client_call_back_url": "string"
   }

بدنه خروجی وب‌سرویس:

.. code-block:: json

   {
     "status": "ok",
     "data": {
       "url": "<لینک درگاه پرداخت>",
       "transaction_id": "string"
     }
   }


استعلام نتیجه پرداخت
--------------------

برای مشاهده نتیجه پرداخت از وب‌سرویس زیر استفاده کنید:

``GET``
``https://api-asato.mihaninsurance.com/insurance-policy/afterpay/{transaction_id}``

.. code-block:: console

   curl -X GET \
     'https://api-asato.mihaninsurance.com/insurance-policy/afterpay/{transaction_id}' \
     -H 'accept: application/json'

بدنه خروجی وب‌سرویس:

.. code-block:: json

   {
     "status": "ok",
     "data": {
       "code": 48694967,
       "amount": 401500,
       "bank_reference_no": "281295302492",
       "date": "1403/05/19",
       "operation_status": 4,
       "is_succeeded": true,
       "transaction_type": "POLICY"
     }
   }

دریافت فایل PDF بیمه‌نامه شخص ثالث
--------------------

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
