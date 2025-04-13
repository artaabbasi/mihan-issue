اطلاعات پایه
===================================

شهر ها
--------

برای دریافت لیست شهر ها از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/city``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/city?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "ecefed04-bffb-47ef-a439-555f4a35aaf3",
          "code": 101,
          "created_at": "2024-08-06T10:33:04.013595Z",
          "updated_at": null,
          "name": "اهر",
          "is_active": true,
          "is_in_free_region": false,
          "province_code": 9455
        }
      ],
      "page": 1,
      "size": 1,
      "count": 902
    }

استان ها
--------

برای دریافت لیست استان ها از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/province``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/province?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "a7383ee1-f459-4506-8dda-b91c3c12cd33",
          "code": 9455,
          "created_at": "2024-08-06T10:33:03.824093Z",
          "updated_at": null,
          "name": "آذربايجان شرقي",
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 33
    }

شرکت های بیمه
--------

برای دریافت لیست شرکت های بیمه از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-corp``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/insurance-corp?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "17cbe855-6b22-43bc-9b07-35c6f4395b5b",
          "code": 320,
          "created_at": "2025-03-13T08:04:52.461287Z",
          "updated_at": null,
          "name": "ندارد",
          "is_active": true
        },
        {
          "id": "ce109782-5f81-44e4-b76a-2d8d5a4114ae",
          "code": 321,
          "created_at": "2025-03-13T08:04:52.461334Z",
          "updated_at": null,
          "name": "ايران",
          "is_active": true
        }
      ],
      "page": 1,
      "size": 2,
      "count": 32
    }

انواع خودرو
--------

برای دریافت لیست انواع خودرو از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-kind``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-kind?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size`` و ``vehicle_group_code`` و ``vehicle_system_code`` و ``search``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "3b39439f-c18e-4d4d-b401-e57a03395ab9",
          "code": 2,
          "created_at": "2025-03-13T08:05:59.800909Z",
          "updated_at": null,
          "name": null,
          "caption": "كاميون تانكر بنز ال پي 36/808",
          "vehicle_category_caption": null,
          "vehicle_system_caption": "بنز",
          "vehicle_group_code": 3,
          "vehicle_system_code": 905,
          "cylinder_count": 4,
          "passenger_count": 2,
          "tonnage": 8,
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 3007
    }

انواع پلاک
--------

برای دریافت لیست انواع پلاک از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-plaque-no-kind``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-plaque-no-kind?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size`` و ``vehicle_group_code``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "415ec7dc-d077-450d-83c0-1ef3163f7b8e",
          "code": 8,
          "created_at": "2025-03-13T08:06:20.642588Z",
          "updated_at": null,
          "name": null,
          "caption": "شخصي",
          "vehicle_group_code": 1,
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 2
    }

کدهای پلاک
--------

برای دریافت لیست کدهای پلاک از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-plaque-no-code``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-plaque-no-code?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "f726ce7f-a388-4279-a3ba-8f1ee6186415",
          "code": 1,
          "created_at": "2025-03-13T09:18:13.912825Z",
          "updated_at": null,
          "name": null,
          "caption": "الف",
          "letter_plaque_code": "01",
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 26
    }

موارد استفاده خودرو
--------

برای دریافت لیست موارد استفاده خودرو از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-use-type``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-use-type?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "4ea9a2e4-b499-48c9-9220-772778f32e38",
          "code": 42,
          "created_at": "2025-03-26T09:06:57.921082Z",
          "updated_at": "2025-03-26T09:10:34.045995Z",
          "name": null,
          "caption": "شخصي",
          "vehicle_group_code": 3,
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 2
    }

گروه های خودرو
--------

برای دریافت لیست گروه های خودرو از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-group``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-group?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size`` و ``search``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "c73bbf3d-a8d9-456f-a0ab-45281cb406ea",
          "code": 1,
          "created_at": "2025-03-13T08:08:14.353809Z",
          "updated_at": null,
          "name": "Savari",
          "caption": "سواري",
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 2
    }

سیستم های خودرو
--------

برای دریافت لیست سیستم های خودرو از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-system``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/vehicle-system?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size`` و ``vehicle_group_code`` و ``search``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "8201f618-7e48-45b2-89d8-acf5e524b2b6",
          "code": 1,
          "created_at": "2025-03-13T08:08:37.276616Z",
          "updated_at": null,
          "name": null,
          "caption": "پرايد",
          "vehicle_group_code": 1,
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 1341
    }

انواع سوخت
--------

برای دریافت لیست انواع سوخت از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/fuel-type``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/fuel-type?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "bb9897a0-10db-4d2f-b16a-6ae035dea893",
          "code": 5222,
          "created_at": "2025-03-13T08:45:11.580951Z",
          "updated_at": null,
          "caption": "بنزيني",
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 3
    }

رنگ ها
--------

برای دریافت لیست رنگ ها از این وبسرویس استفاده کنید:

    ``GET``
    ``https://api-asato.mihaninsurance.com/insurance-policy-static/color``

.. code-block:: console

   curl -X 'GET' \
    'https://api-asato.mihaninsurance.com/insurance-policy-static/color?page=1&size=1' \
    -H 'accept: application/json'

: پارامتر های ورودی

    ``page`` و ``size``

خروجی وب سرویس:

.. code-block:: console

    {
      "status": "ok",
      "data": [
        {
          "id": "717ec225-d2c0-431f-9d65-91a78b6f1a19",
          "code": 1,
          "created_at": "2025-03-13T08:39:19.761160Z",
          "updated_at": null,
          "name": "سفيد",
          "caption": "سفيد",
          "is_active": true
        }
      ],
      "page": 1,
      "size": 1,
      "count": 744
    }
