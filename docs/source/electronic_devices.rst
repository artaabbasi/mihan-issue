تجهیزات الکترونیک
=====

طرح ها
------------

برای دریافت طرح های مربوط به تجهیزات الکترونیک از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=55``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-plan?insurance_type_code=55&page=1&size=1' \
    -H 'accept: application/json'
: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

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
                "special_condition_terms": "مدل : آبي\n- بيمه موبايل طبق توافقنامه 1403\n- بيمه در موارد ذيل تعهدي نخواهد داشت:\n1- خسارات ناشي از فرسودگي در اثر استعمال و خط و خش بر روي دستگاه.\n2- خسارات مربوط به کاهش يا از بين رفتن اطلاعات و هزينه ابقا مجدد اطلاعات (بخش نرم افزاري).\n3- خسارتهاي ناشي از تعمير يا دستکاري دستگاه توسط افراد غير متخصص و غير مجاز.\n4- خسارتهاي ناشي از عيوب ذاتي (موارد تحت پوشش گارانتي)\n- خطرات تحت پوشش:\n آسيب با شکست فيزيکي LCD تلفن همراه- سرقت کلي- آبديدگي\n- مدت اعتبار بيمه نامه:\n يکسال شمسي از تاريخ صدور گواهي/ بيمه نامه\n- شروع پوشش: 20 روز پس از بازديد سلامت و صدور گواهي /بيمه نامه خواهد بود.\n- فرانشيز:\n خسارات جزئي و کلي 15% حداقل 5.000.000 ريال در هر حادثه\n- حد غرامت:\n حد پرداخت خسارت هر مورد بيمه در اين بيمه نامه حداکثر تا (850.000.000 ريال/ ارزش واقعي) هرکدام که کمترباشد خواهد بود.\n- ساير شرايط:\n1- مهلت اعلام خسارت حداکثر 14روز پس ازحادثه در طول مدت بيمه نامه مي باشد.\n2- شروع تعهدات بيمه نامه منوط به تکميل بازديد و ارائه گواهي صادره خواهد بود و مسئول حسن انجام کار بر عهده مجري توافقنامه خواهد بود.\n3- گوشي هاي رجيستر نشده  تحت پوشش اين بيمه نامه نمي باشد.\n4- پرداخت هرگونه خسارت منوط به ارائه مستندات کامل از قبيل تصاوير سلامت- جعبه و ساير مدارک مثبته خواهد بود.\n5- پرداخت خسارت به ذينفع بيمه نامه و با درخواست کتبي بيمه گذار خواهد بود.\n6- قطعي شدن ساير شرايط و حدود و حق بيمه و رسيدگي خسارت مطابق شرايط توافقنامه فوق الذکر بوده و هرگونه ادعا خارج از توافقنامه مذکور غير قابل رسيدگي و بر عهده مجري (کارگزاري رسمي سرزمين بيمه) خواهد بود."
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
              },
              {
                "franchise_type_code": 29,
                "apply_method_code": 27,
                "franchise": 15,
                "min_franchise_amount": 15000000,
                "franchise_cov_type_code": 49
              }
            ]
          },
          "insurance_type": {
            "id": "65c60f8c-1c28-4333-a9d0-c2b30064b195",
            "code": 55,
            "created_at": "2024-06-15T09:33:06.718061Z",
            "updated_at": null,
            "title": "تجهيزات الکترونيکي",
            "name": "مهندسي",
            "icon": "nan",
            "is_active": true,
            "type": "PROPERTY",
            "is_buy_active": null
          },
          "festival": null
        }
      ],
      "page": 1,
      "size": 1,
      "count": 1
    }


ساخت درخواست صدور بیمه نامه
----------------

برای ساخت فاکتور صدور بیمه نامه :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device``

.. code-block:: console

   curl -X 'POST' \
    'https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device' \
    -H 'accept: application/json' \
    -H 'Authorization: Bearer <توکن شما که در مرحله احراز هویت گرفتید> \
    -H 'Content-Type: application/json'

برای بروزرسانی فاکتور صدور بیمه نامه :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/<آیدی صدور بیمه نامه>``

.. code-block:: console

   curl -X 'PATCH' \
    'https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/<آیدی صدور بیمه نامه>' \
    -H 'accept: application/json' \
    -H 'Authorization: Bearer <توکن شما که در مرحله احراز هویت گرفتید> \
    -H 'Content-Type: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "insurance_plan_code": <کد طرح انتخابی که در مرحله قبل گرفتید>,
      "insurer_customer_code": <کد بیمه گزار>,
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
      "attachment_files": [
        "string"
      ],
      "insured_devices": [
        {
          "row": 0, // ایندکس ورودی با شروع از یک
          "caption": "string", // نام یا توضیحات دیوایس
          "address": "string", // آدرس
          "count": 0, // تعداد ایتم های ورودی
          "brand": "string",//برند موبایل
          "model": "string",// مدل دستگاه
          "manufacturer_country_code": 0,//کد کشور 
          "production_year": 0,// سال ساخت دستگاه
          "serial_no": "string",//شماره سریال
          "insured_value": 0,//مبلغ ارزش دستگاه
          "components": [
            {
              "component_code": 11 ,//مقدار پیش فرض ۱۱
              "brand": "string",//برند
              "serial_no": "string",//شماره سریال
              "count": 0, // شماره ایندکس شروع از 1 
              "insured_value": 0 //ارزش 
            }
          ]
        }
      ]
    }

بدنه خروجی وبسرویس :


.. code-block:: console

    {
      "status": "ok",
      "data": {
        "id": "4e868dea-cab4-4e7d-a067-f43fe3246033", # آیدی صدور بیمه نامه
        "insurance_factor_id": "083ba303-b9c6-412b-a8d7-e1b59f96df10", # آیدی فاکتور بیمه نامه
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
        "proposal_date": "string",
        "proposal_number": 0,
        "attachment_files": [
          "string"
        ],
        "insured_devices": [
          {
            "row": 0,
            "caption": "string",
            "address": "string",
            "count": 0,
            "brand": "string",
            "model": "string",
            "manufacturer_country_code": 0,
            "production_year": 0,
            "serial_no": "string",
            "insured_value": 0,
            "components": [
              {
                "component_code": 0,
                "brand": "string",
                "serial_no": "string",
                "count": 0,
                "insured_value": 0
              }
            ]
          }
        ],
        "response": {},
        "insurance_factor": {
          "id": "083ba303-b9c6-412b-a8d7-e1b59f96df10",
          "state": "CREATED",
          "user_id": "b2ecc23e-3df4-4576-9a03-9e6e2f70f2e8",
          "insurance_type_code": 55,
          "insurance_plan_code": 0,
          "insurer_customer_code": 0,
          "insured_customer_code": null,
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
          "created_at": "2025-03-17T08:00:48.992850Z",
          "updated_at": null
        },
        "city": null
      }
    }

ثبت درخواست در فناوران
----------------

با فراخوانی این وب سرویس بیمه نامه در فناوران ثبت میشود :

    ``POST``
    ``https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/submit/<آیدی صدور بیمه نامه>``


.. code-block:: console

   curl -X 'POST' \
      'https://api-asato.mihaninsurance.com/insurance_policy_buy/electronic-device/submit/<آیدی صدور بیمه نامه>' \
      -H 'accept: application/json'

بدنه ورودی :

.. code-block:: console

    {
      "status": "ok",
      "data": {
        "id": "338f403d-3b19-42e2-8f21-01967ad857bb",
        "insurance_factor_id": "888f3377-076d-4f59-a291-0817382d9166",
        "previous_policy_ci_number": null,
        "extended_policy_code": null,
        "previous_policy_no": null,
        "previous_insurance_corp_code": 320,
        "insured_city_code": 9132,
        "insured_address": "سراسر کشور",
        "beneficiary_code": null,
        "is_in_free_region": 0,
        "free_region_code": null,
        "proposal_date": "1403/12/14",
        "proposal_number": 123456789,
        "attachment_files": [],
        "insured_devices": [
          {
            "row": 1,
            "caption": "اپل مدل Iphone 14 ظرفیت ۲۵۶ گیگابایت ",
            "address": "سراسر کشور",
            "count": 1,
            "brand": "Apple",
            "model": "Iphone 14",
            "manufacturer_country_code": 9299,
            "production_year": 1403,
            "serial_no": "IMEI356663515068166",
            "insured_value": 850000000,
            "components": []
          }
        ],
        "response": {
          "AgentId": 9310,
          "AvgRatePartOne": 2.67,
          "AvgRatePartTwo": 0,
          "BeginDate": "1403/12/14",
          "BeneficiaryId": null,
          "CalcKindId": 223,
          "CINumber": null,
          "ContractId": 4436,
          "CptlMoneyUnitRateId": 1,
          "CptlMoneyUnitRateKindId": 701,
          "CustomerId": 13869987,
          "Discount": 0,
          "DiscountPrm": 0,
          "Duration": 365,
          "EconomicNo": null,
          "EndDate": "1404/12/13",
          "EndoNo": 0,
          "ExtendedPolicyId": null,
          "Franchise": [
            {
              "ApplyMethodId": 26,
              "Franchise": 15,
              "FranchiseCovTypeId": 49,
              "FranchiseTypeId": 27,
              "Id": 3974,
              "MinFranchiseAmount": 5000000,
              "PolicyId": 3857561,
              "PolicyVerNo": 0
            },
            {
              "ApplyMethodId": 27,
              "Franchise": 15,
              "FranchiseCovTypeId": 49,
              "FranchiseTypeId": 29,
              "Id": 3975,
              "MinFranchiseAmount": 15000000,
              "PolicyId": 3857561,
              "PolicyVerNo": 0
            }
          ],
          "FreeRegionId": null,
          "InsuredAddress": null,
          "InsuredCityId": 9132,
          "InsuredDevices": [
            {
              "Address": "سراسر کشور",
              "Brand": "Apple",
              "Caption": "اپل مدل Iphone 14 ظرفيت 256 گيگابايت",
              "Count": 1,
              "ElectronicDeviceTypeId": 8,
              "Id": 221182,
              "InsuredValue": 850000000,
              "ManufacturerCountryId": null,
              "Model": null,
              "PolicyId": 3857561,
              "PolicyVerNo": 0,
              "Premium": 2272727,
              "ProductionYear": 1403,
              "Rate": 2.673796,
              "RiskGroupId": 6,
              "SerialNo": "IMEI356663515068166"
            }
          ],
          "IsInFreeRegion": 0,
          "IssuDate": null,
          "LiabitityCovRate": 0,
          "MarketerId": null,
          "OpUnitId": 220,
          "PartOnePrm": 2272727,
          "PartTwoPrm": 0,
          "PolicyId": 3857561,
          "PolicyIssuDate": null,
          "PolicyNo": null,
          "PolicyOpUnitId": 220,
          "PolicyUsageTypeId": null,
          "PolicyVerNo": 0,
          "Premium": 2272727,
          "PreviousInsuranceCorpId": 320,
          "PreviousPolicyCINumber": null,
          "PreviousPolicyNo": null,
          "PrmMoneyUnitRateId": 1,
          "PrmMoneyUnitRateKindId": 701,
          "ProposalDate": "1403/12/14",
          "ProposalNo": "123456789",
          "SpecialConditions": [
            {
              "Id": 2893,
              "LanguageId": 64,
              "PolicyId": 3857561,
              "PolicyVerNo": 0,
              "SpecialConditionId": 1,
              "SpecialConditionTerms": "شماره گواهي: "
            }
          ],
          "Status": 635,
          "Tax": 136364,
          "Toll": 90909,
          "TotalPremium": 2500000,
          "TranTypeId": 226
        },
        "insurance_factor": {
          "id": "888f3377-076d-4f59-a291-0817382d9166",
          "state": "SUBMITTED",
          "user_id": "aebf43f5-17d9-4f73-891e-5ad74c14077d",
          "insurance_type_code": 55,
          "insurance_plan_code": 1,
          "insurer_customer_code": 13869987,
          "insured_customer_code": null,
          "other_customer_code": null,
          "location_code": null,
          "agent_code": null,
          "marketer_code": null,
          "insurance_policy_code": 3857561,
          "policy_ver_no": 0,
          "tax": 136364,
          "toll": 90909,
          "premium": 2500000,
          "begin_date": "1403/12/14",
          "end_date": "1404/12/13",
          "insurer": {
            "id": "8d0cf530-9770-495a-976c-71ac81e8b6e1",
            "code": 13869987,
            "created_at": "2025-07-28T13:09:07.219974Z",
            "updated_at": null,
            "ad_birth_day": null,
            "ad_birth_month": null,
            "ad_birth_year": null,
            "address": "استان تهران، شهرستان تهران، بخش مرکزي، شهر تهران، عباس آباد-انديشه، خيابان شهيد خليل حسيني، خيابان شهيد دکتر بهشتي، پلاک 206، طبقه همکف، واحد شرقي",
            "birth_city_code": null,
            "birth_day": null,
            "birth_month": null,
            "birth_year": null,
            "cii_mobile_status": 2126,
            "cii_validation_status": 2128,
            "city_code": 701,
            "company_code": "14012399280",
            "economic_code": null,
            "education_field": null,
            "education_level_code": null,
            "email": null,
            "en_address": null,
            "en_last_name": null,
            "en_name": null,
            "father_name": null,
            "fax": null,
            "gender_code": null,
            "identity_no": null,
            "identity_no_issu_place": null,
            "is_iranian": 1,
            "is_main_person": 1,
            "is_valid": 1,
            "is_verified": 1,
            "job_address": null,
            "last_name": null,
            "legal_person_registration_date": "1402/04/21",
            "legal_person_registry_office_status": "فعال",
            "main_person_code": null,
            "marital_status": null,
            "mobile": "09120802580",
            "name": "گروه زرين صنعت ارتباط هوشمند",
            "national_code": null,
            "nationality_code": null,
            "naturalized_code": null,
            "ownership_code": 56,
            "passport_no": null,
            "person_kind_code": 47,
            "postal_code": "1577835911",
            "register_no": "615368",
            "religion_code": null,
            "tel": null,
            "city": null,
            "roles": []
          },
          "insured": null,
          "other": null,
          "insurance_plan": {
            "id": "11642ee6-ec0f-468b-bb74-fbf37e23d7f7",
            "code": 1,
            "created_at": "2025-02-19T14:21:58.943705Z",
            "updated_at": null,
            "name": null,
            "insurance_type_code": 55,
            "is_marketable": null,
            "is_active": true,
            "festival_code": null,
            "payload": {
              "name": null,
              "code": 1,
              "is_marketable": true,
              "is_active": true,
              "festival_code": null,
              "usage_type": null,
              "location_access_type": null,
              "agent_access_type": null,
              "marketer_access_type": null,
              "allowed_users_ids": null,
              "contract_code": 4436,
              "electronic_device_type_code": 8,
              "risk_group_code": 6,
              "calc_kind_code": 221,
              "liability_cov_rate": 0,
              "rate": 2.673796,
              "liability_covs": [],
              "clauses": [],
              "special_conditions": [
                {
                  "special_condition_code": 1,
                  "language_code": 64,
                  "special_condition_terms": "مدل : آبي\n- بيمه موبايل طبق توافقنامه 1403\n- بيمه در موارد ذيل تعهدي نخواهد داشت:\n1- خسارات ناشي از فرسودگي در اثر استعمال و خط و خش بر روي دستگاه.\n2- خسارات مربوط به کاهش يا از بين رفتن اطلاعات و هزينه ابقا مجدد اطلاعات (بخش نرم افزاري).\n3- خسارتهاي ناشي از تعمير يا دستکاري دستگاه توسط افراد غير متخصص و غير مجاز.\n4- خسارتهاي ناشي از عيوب ذاتي (موارد تحت پوشش گارانتي)\n- خطرات تحت پوشش:\n آسيب با شکست فيزيکي LCD تلفن همراه- سرقت کلي- آبديدگي\n- مدت اعتبار بيمه نامه:\n يکسال شمسي از تاريخ صدور گواهي/ بيمه نامه\n- شروع پوشش: 20 روز پس از بازديد سلامت و صدور گواهي /بيمه نامه خواهد بود.\n- فرانشيز:\n خسارات جزئي و کلي 15% حداقل 5.000.000 ريال در هر حادثه\n- حد غرامت:\n حد پرداخت خسارت هر مورد بيمه در اين بيمه نامه حداکثر تا (850.000.000 ريال/ ارزش واقعي) هرکدام که کمترباشد خواهد بود.\n- ساير شرايط:\n1- مهلت اعلام خسارت حداکثر 14روز پس ازحادثه در طول مدت بيمه نامه مي باشد.\n2- شروع تعهدات بيمه نامه منوط به تکميل بازديد و ارائه گواهي صادره خواهد بود و مسئول حسن انجام کار بر عهده مجري توافقنامه خواهد بود.\n3- گوشي هاي رجيستر نشده  تحت پوشش اين بيمه نامه نمي باشد.\n4- پرداخت هرگونه خسارت منوط به ارائه مستندات کامل از قبيل تصاوير سلامت- جعبه و ساير مدارک مثبته خواهد بود.\n5- پرداخت خسارت به ذينفع بيمه نامه و با درخواست کتبي بيمه گذار خواهد بود.\n6- قطعي شدن ساير شرايط و حدود و حق بيمه و رسيدگي خسارت مطابق شرايط توافقنامه فوق الذکر بوده و هرگونه ادعا خارج از توافقنامه مذکور غير قابل رسيدگي و بر عهده مجري (کارگزاري رسمي سرزمين بيمه) خواهد بود."
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
                },
                {
                  "franchise_type_code": 29,
                  "apply_method_code": 27,
                  "franchise": 15,
                  "min_franchise_amount": 15000000,
                  "franchise_cov_type_code": 49
                }
              ]
            },
            "usage_type": null,
            "location_access_type": null,
            "agent_access_type": null,
            "marketer_access_type": null,
            "allowed_users_ids": null,
            "insurance_type": {
              "id": "65c60f8c-1c28-4333-a9d0-c2b30064b195",
              "code": 55,
              "created_at": "2024-06-15T09:33:06.718061Z",
              "updated_at": null,
              "title": "تجهيزات الکترونيکي",
              "name": "مهندسي",
              "icon": "nan",
              "is_active": true,
              "type": "PROPERTY",
              "is_buy_active": null
            },
            "festival": {
              "id": null,
              "code": null,
              "name": null,
              "created_at": null,
              "updated_at": null
            },
            "allowed_users": null
          },
          "location": null,
          "agent": null,
          "marketer": null,
          "created_at": "2025-03-04T11:07:31.610194Z",
          "updated_at": "2025-03-04T11:14:58.245934Z"
        },
        "city": null
      }
    }



پرداخت فاکتور در فناوران 
----------------

 با فراخوانی این وب سرویس بیمه نامه در فناوران پرداخت میشود با این تفاوت که ایدی تراکنش هم جهت استعلام پرداخت بازگردانی میشود: 

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
      "factor_id": "083ba303-b9c6-412b-a8d7-e1b59f96df10",
      "client_call_back_url": "string"
    }

بدنه خروجی وبسرویس :


.. code-block:: console

    {
      "status": "ok",
      "data": {
        "url": "<لینک درگاه پرداخت>",
        "transaction_id": "string"//ایدی تراکنش جهت استعلام پرداخت
      }
    }


استعلام نتیجه پرداخت 
----------------
با فراخوانی این وب سرویس نتیجه پرداخت قابل مشاهده خواهد بود.: 

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy/afterpay/{transaction_id}``


.. code-block:: console

   curl -X 'GET' \
  'https://api-asato.mihaninsurance.com/insurance-policy/afterpay/{transaction_id}' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json'



بدنه خروجی وبسرویس :


.. code-block:: console

    {
      "status": "ok",
      "data": {
        "code": 48694967,
        "amount": 401500,
        "bank_reference_no": "281295302492",
        "date": "1403/05/19",
        "operation_status": 4,
        "op_unit_id": 220,
        "person_id": 13616189,
        "person_role_id": 161,
        "is_succeeded": true,//موفق بودن
        "transaction_type": "POLICY",
        "transaction_related_codes": [
          3726886
        ],
        "insurance_factor_id": "d1817208-4839-48d8-acd3-5d213155a1af",
        "insurance_type_code": 17
      }
    }

