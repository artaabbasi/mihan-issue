شخص ثالث
=====

طرح ها
------------

برای دریافت طرح ها از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=5``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=5&page=1&size=1' \
    -H 'accept: application/json'
: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

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


ساخت درخواست صدور بیمه نامه
----------------

برای ساخت فاکتور صدور بیمه نامه :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party``

.. code-block:: console

   curl -X 'POST' \
    'https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party' \
    -H 'accept: application/json' \
    -H 'Authorization: Bearer <توکن شما که در مرحله احراز هویت گرفتید> \
    -H 'Content-Type: application/json'

برای بروزرسانی فاکتور صدور بیمه نامه :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/<آیدی صدور بیمه نامه>``

.. code-block:: console

   curl -X 'PATCH' \
    'https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/<آیدی صدور بیمه نامه>' \
    -H 'accept: application/json' \
    -H 'Authorization: Bearer <توکن شما که در مرحله احراز هویت گرفتید> \
    -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

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
بدنه خروجی وبسرویس :

.. code-block:: console

    {
      "status": "ok",
      "data": {
        "id": "383a5f94-3452-4da1-a1fe-6059e39cb846",
        "insurance_factor_id": "d2984a7e-85c9-4089-a392-ff58e11bab57",
        "is_fetch_from_centinsure": false,
        "national_code": null,
        "previous_policy_status": null,
        "previous_policy_ci_number": null,
        "previous_policy_begin_date": null,
        "previous_policy_end_date": null,
        "previous_policy_no": null,
        "previous_policy_discount_duration": null,
        "previous_policy_discount_percent": null,
        "has_dmg": null,
        "life_dmg_count": null,
        "financial_dmg_count": null,
        "driver_accidents_dmg_count": null,
        "previous_policy_driver_accidents_discount_duration": null,
        "previous_policy_driver_accidents_discount_percent": null,
        "accident_violations_count": null,
        "form_seri": null,
        "form_serial": null,
        "transferor_policy_ci_number": null,
        "transferor_policy_no": null,
        "transferor_policy_end_date": null,
        "transferor_discount_duration": null,
        "transferor_discount_percent": null,
        "driver_accidents_transfer_discount_duration": null,
        "driver_accidents_transfer_discount_percent": null,
        "transferor_plaque_serial": null,
        "transferor_plaque_right_no": null,
        "transferor_plaque_left_no": null,
        "economic_no": null,
        "label_serial_no": null,
        "doc_package_key": null,
        "transferor_plaque_no": null,
        "plaque_owner_code": null,
        "transferor_person_code": null,
        "extended_policy_code": null,
        "previous_insurance_corp_code": 320,
        "agent_code": 220,
        "is_in_free_region": null,
        "free_region_code": null,
        "financial_cov": null,
        "life_cov": null,
        "driver_accidents_cov": null,
        "has_transfer_discount": null,
        "reason_for_has_not_previous_policy_code": null,
        "transferor_relation_type_code": null,
        "transferor_insurance_corp_code": null,
        "transferor_policy_code": null,
        "transferor_tariff_group_code": null,
        "transferor_plaque_sample_code": null,
        "transferor_plaque_middle_code_code": null,
        "marketer_code": null,
        "policy_usage_type_code": null,
        "transferor_plaque_city_code": null,
        "vehicle_code": null,
        "vehicle_plaque_serial": null,
        "vehicle_plaque_left_no": null,
        "vehicle_plaque_right_no": null,
        "vehicle_plaque_date": null,
        "vehicle_motor_no": null,
        "vehicle_chassis_no": null,
        "vehicle_built_year": null,
        "vehicle_vin": null,
        "vehicle_plaque_no": null,
        "vehicle_third_party_spare_count": null,
        "vehicle_spare_desc": null,
        "vehicle_spare_plaque_no": null,
        "vehicle_spare_plaque_date": null,
        "vehicle_spare_plaque_serial": null,
        "vehicle_spare_plaque_right_no": null,
        "vehicle_spare_plaque_left_no": null,
        "vehicle_spare_plaque_vin": null,
        "vehicle_kind_code": null,
        "vehicle_use_type_code": null,
        "vehicle_plaque_sample_code": null,
        "vehicle_plaque_middle_code": null,
        "vehicle_color_code": null,
        "vehicle_fuel_type_code": null,
        "vehicle_plaque_city_code": null,
        "vehicle_has_third_party_spare": null,
        "vehicle_spare_plaque_sample_code": null,
        "vehicle_spare_plaque_middle_code": null,
        "vehicle_spare_plaque_city_code": null,
        "vehicle_plaque_kind_code": null,
        "response": {},
        "insurance_factor": {
          "id": "d2984a7e-85c9-4089-a392-ff58e11bab57",
          "state": "CREATED",
          "user_id": "380c6a5e-4ae1-4e4a-b98a-f4f72a7ab550",
          "insurance_type_code": 5,
          "insurance_plan_code": 0,
          "insurer_customer_code": 0,
          "insured_customer_code": null,
          "location_code": 220,
          "insurance_policy_code": null,
          "policy_ver_no": null,
          "tax": null,
          "toll": null,
          "premium": null,
          "begin_date": null,
          "end_date": null,
          "insurer": {
            "id": "397cab0e-d295-4c7c-80fe-6b9ce9b424ac",
            "code": 0,
            "created_at": "2025-02-09T12:21:37.650943Z",
            "updated_at": null,
            "ad_birth_day": null,
            "ad_birth_month": null,
            "ad_birth_year": null,
            "address": "تهران -خيابان شهيد خالد اسلامبولي، نبش خيابان بيست و هشتم ، پلاک 90",
            "birth_city_code": null,
            "birth_day": null,
            "birth_month": null,
            "birth_year": null,
            "cii_mobile_status": 2126,
            "cii_validation_status": 2128,
            "city_code": null,
            "company_code": "10103698106",
            "economic_code": "None",
            "education_field": "None",
            "education_level_code": null,
            "email": null,
            "en_address": null,
            "en_last_name": null,
            "en_name": null,
            "father_name": null,
            "fax": null,
            "gender_code": null,
            "identity_no": "None",
            "identity_no_issu_place": null,
            "is_iranian": 1,
            "is_main_person": 1,
            "is_valid": 1,
            "is_verified": 1,
            "job_address": null,
            "last_name": null,
            "legal_person_registration_date": "1387/06/18",
            "legal_person_registry_office_status": "فعال",
            "main_person_code": null,
            "marital_status": "None",
            "mobile": null,
            "name": "بيمه ميهن",
            "national_code": null,
            "nationality_code": null,
            "naturalized_code": null,
            "ownership_code": null,
            "passport_no": "None",
            "person_kind_code": 47,
            "postal_code": "1511916413",
            "register_no": "330902",
            "religion_code": null,
            "tel": "88505864",
            "city": null,
            "roles": []
          },
          "insured": null,
          "insurance_plan": {
            "id": null,
            "code": null,
            "created_at": null,
            "updated_at": null,
            "insurance_type_code": null,
            "festival_code": null,
            "payload": null,
            "insurance_type": {
              "id": null,
              "code": null,
              "created_at": null,
              "updated_at": null,
              "title": null,
              "name": null,
              "icon": null,
              "is_active": null,
              "type": null,
              "is_buy_active": null
            },
            "festival": {
              "id": null,
              "code": null,
              "name": null,
              "created_at": null,
              "updated_at": null
            }
          },
          "created_at": "2025-04-13T14:44:10.623036Z",
          "updated_at": null
        },
        "previous_insurance_corp": {
          "id": "17cbe855-6b22-43bc-9b07-35c6f4395b5b",
          "code": 320,
          "created_at": "2025-03-13T08:04:52.461287Z",
          "updated_at": null,
          "name": "ندارد",
          "is_active": true
        },
        "vehicle_kind": null,
        "vehicle_use_type": null,
        "vehicle_fuel_type": null,
        "vehicle_plaque_middle": null,
        "vehicle_color": null,
        "vehicle_plaque_city": null,
        "vehicle_plaque_kind": null
      }
    }


ثبت درخواست در فناوران
----------------

با فراخوانی این وب سرویس بیمه نامه در فناوران ثبت میشود :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/submit/<آیدی صدور بیمه نامه>``


.. code-block:: console

   curl -X 'GET' \
      'https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/submit/<آیدی صدور بیمه نامه>' \
      -H 'accept: application/json'

استعلام قیمت درخواست در فناوران
----------------

با فراخوانی این وب سرویس بیمه نامه در فناوران استعلام قیمت میشود :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/check_price/<آیدی صدور بیمه نامه>``


.. code-block:: console

   curl -X 'GET' \
      'https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/check_price/<آیدی صدور بیمه نامه>' \
      -H 'accept: application/json'

بدنه خروجی وبسرویس :


.. code-block:: console

    {
      "status": "ok",
      "data": {
        "code": 0,
        "begin_date": "string",
        "end_date": "string",
        "calc_kind_code": 0,
        "built_year": 0,
        "final_fund_prm": 0,
        "financial_cov": 0,
        "financial_dmg_count": 0,
        "financial_final_extra_prm": 0,
        "free_region_code": 0,
        "has_spare": 0,
        "is_in_free_region": 0,
        "is_new_car": 0,
        "life_cov": 0,
        "life_dmg_count": 0,
        "life_final_extra_prm": 0,
        "driver_accidents_cov": 0,
        "driver_accidents_dmg_count": 0,
        "driver_accidents_dmg_final_extra_prm": 0,
        "driver_accidents_wait_duration": 0,
        "plaque_date": "string",
        "plaque_kind_code": 0,
        "plaque_sample_code": 0,
        "policy_driver_accidents_duration": 0,
        "policy_driver_accidents_percent": 0,
        "policy_third_party_duration": 0,
        "policy_third_party_percent": 0,
        "previous_policy_begin_date": "string",
        "previous_insurance_corp_code": 0,
        "previous_policy_discount_duration": 0,
        "previous_policy_discount_percent": 0,
        "previous_policy_end_date": "string",
        "previous_policy_driver_accidents_discount_duration": 0,
        "previous_policy_driver_accidents_discount_percent": 0,
        "spare_count": 0,
        "spare_plaque_date": "string",
        "tax": 0,
        "third_party_final_prm": 0,
        "third_party_wait_duration": 0,
        "toll": 0,
        "total_premium": 0,
        "used_code": 0,
        "vehicle_kind_code": 0
      }
    }

پرداخت فاکتور در فناوران
----------------

با فراخوانی این وب سرویس بیمه نامه در فناوران ثبت میشود :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/factor/pay``


.. code-block:: console

   curl -X 'POST' \
  'https://api-asato.mihaninsurance.com/insurance_policy_buy/factor/pay' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "factor_id": "083ba303-b9c6-412b-a8d7-e1b59f96df10"
    }

بدنه خروجی وبسرویس :


.. code-block:: console

    {
      "status": "ok",
      "data": <لینک درگاه پرداخت>
    }


دریافت فایل PDF بیمه‌نامه شخص ثالث
====================================

با فراخوانی این وب‌سرویس، فایل PDF بیمه‌نامه شخص ثالث بر اساس کد رایانه بیمه‌نامه دریافت می‌شود.

درخواست
--------

``GET`` ``https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/print_by_code/{policy_code}/``

**پارامترهای مسیر (Path Parameters):**

- ``policy_code`` (اجباری)  
  کد رایانه بیمه‌نامه که باید در URL جایگذاری شود.

**هدرهای درخواست:**

.. code-block:: http

    accept: application/json
    Authorization: Bearer {token}

پاسخ
-----

در صورت موفقیت، پاسخ شامل **فایل PDF بیمه‌نامه** با `Content-Type: application/pdf` خواهد بود.

مثال (cURL)
-----------

.. code-block:: bash

    curl -X 'GET' \
      'https://api-asato.mihaninsurance.com/insurance_policy_buy/third-party/print_by_code/12345ABC/' \
      -H 'accept: application/json' \
      -H 'Authorization: Bearer your_access_token_here' \
      --output policy.pdf
