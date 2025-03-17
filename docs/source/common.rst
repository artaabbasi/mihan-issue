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
