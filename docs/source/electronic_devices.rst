تجهیزات الکترونیک
=================

طرح‌ها
-------

برای دریافت طرح‌های مربوط به تجهیزات الکترونیک از وب‌سرویس زیر استفاده کنید:

``GET``
``https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=55``

نمونه درخواست:

.. code-block:: console

   curl -X GET \
     'https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=55&page=1&size=1' \
     -H 'accept: application/json'

پارامترهای ورودی:

- ``page`` : شماره صفحه
- ``size`` : تعداد رکورد در هر صفحه

خروجی وب‌سرویس:

.. code-block:: json

   {
     "status": "ok",
     "data": [
       {
         "id": "11642ee6-ec0f-468b-bb74-fbf37e23d7f7",
         "code": 1,
         "created_at": "2025-02-19T14:21:58.943705Z",
         "updated_at": null,
         "insurance_type_code": 55,
         "festival_code": null,
         "payload": {
           "code": 1,
           "contract_code": 4436,
           "electronic_device_type_code": 8,
           "risk_group_code": 6,
           "agent_code": 220,
           "calc_kind_code": 221,
           "liability_cov_rate": 0,
           "rate": 2.673796,
           "liability_covs": [],
           "clauses": [],
           "special_conditions": [
             {
               "special_condition_code": 1,
               "language_code": 64,
               "special_condition_terms": "..."
             }
           ],
           "risks": [],
           "franchises": [
             {
               "franchise_type_code": 27,
               "apply_method_code": 26,
               "franchise": 15,
               "min_franchise_amount": 5000000,
               "franchise_cov_type_code": 49
             }
           ]
         },
         "insurance_type": {
           "code": 55,
           "title": "تجهيزات الکترونيکي",
           "type": "PROPERTY"
         }
       }
     ],
     "page": 1,
     "size": 1,
     "count": 1
   }


ساخت درخواست صدور بیمه‌نامه
----------------------------

برای ساخت فاکتور صدور بیمه‌نامه از وب‌سرویس زیر استفاده کنید:

``POST``
``https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device``

نمونه درخواست:

.. code-block:: console

   curl -X POST \
     'https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device' \
     -H 'accept: application/json' \
     -H 'Authorization: Bearer <توکن دریافتی>' \
     -H 'Content-Type: application/json'

برای بروزرسانی فاکتور صدور بیمه‌نامه:

``PATCH``
``https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/<آیدی صدور بیمه‌نامه>``

.. code-block:: console

   curl -X PATCH \
     'https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/<آیدی صدور بیمه‌نامه>' \
     -H 'accept: application/json' \
     -H 'Authorization: Bearer <توکن دریافتی>' \
     -H 'Content-Type: application/json'

بدنه ورودی:

.. code-block:: json

   {
     "insurance_plan_code": 1,
     "insurer_customer_code": 12345,
     "previous_policy_ci_number": 0,
     "extended_policy_code": 0,
     "previous_policy_no": 0,
     "previous_insurance_corp_code": 320,
     "marketer_code": 0,
     "insured_city_code": 0,
     "insured_address": "string",
     "beneficiary_code": 0,
     "is_in_free_region": 0,
     "free_region_code": 0,
     "proposal_number": 0,
     "proposal_date": "string",
     "attachment_files": [],
     "insured_devices": [
       {
         "row": 1,
         "caption": "string",
         "address": "string",
         "count": 1,
         "brand": "string",
         "model": "string",
         "manufacturer_country_code": 0,
         "production_year": 0,
         "serial_no": "string",
         "insured_value": 0,
         "components": [
           {
             "component_code": 11,
             "brand": "string",
             "serial_no": "string",
             "count": 1,
             "insured_value": 0
           }
         ]
       }
     ]
   }

بدنه خروجی وب‌سرویس:

.. code-block:: json

   {
     "status": "ok",
     "data": {
       "id": "4e868dea-cab4-4e7d-a067-f43fe3246033",
       "insurance_factor_id": "083ba303-b9c6-412b-a8d7-e1b59f96df10",
       "insurance_factor": {
         "state": "CREATED"
       }
     }
   }


ثبت درخواست در فناوران
----------------------

با فراخوانی این وب‌سرویس، بیمه‌نامه در سیستم فناوران ثبت می‌شود:

``POST``
``https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/submit/<آیدی صدور بیمه‌نامه>``

.. code-block:: console

   curl -X POST \
     'https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/submit/<آیدی صدور بیمه‌نامه>' \
     -H 'accept: application/json'

خروجی وب‌سرویس:

.. code-block:: json

   {
     "status": "ok",
     "data": {
       "insurance_factor": {
         "state": "SUBMITTED",
         "insurance_policy_code": 3857561
       }
     }
   }


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
