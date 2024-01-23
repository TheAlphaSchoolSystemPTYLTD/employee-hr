**getLeaveBalances**
----
  Returns an array of structured Leave Balances details in JSON format.

* **Version History:**

    Version | Description
    --- | --- |
    TASS v59.02 | New V3 API endpoint released.

* **Version:**

    3

* **Permission:**

    Payroll > Employees > --- Accruals tab > View

* **Method:**

	`GET | POST`

*  **Parameters:**

    Parameter Name | Type | Mandatory | Notes
    --- | :---: | :---: | --- |
    code | string | Yes | Employee code.

* **Success Response:**

    ```javascript
      {
        "leave_balances": [
                {
                  "accrual_code": "ANN",
                  "accrual_start_date": "04/09/2000",
                  "unit": "Hours",
                  "description": "Annual Leave Accrual",
                  "quantity_as_at_date": "15/05/2009",
                  "entitlement_quantity": 0
                },
                {
                  "accrual_code": "LSC",
                  "accrual_start_date": "04/09/2000",
                  "unit": "Hours",
                  "description": "Long Service Leave (C)",
                  "quantity_as_at_date": "21/08/2020",
                  "entitlement_quantity": 494.95418
                },
                {
                  "accrual_code": "SCK",
                  "accrual_start_date": "04/09/2000",
                  "unit": "Hours",
                  "description": "Sick Leave",
                  "quantity_as_at_date": "21/08/2020",
                  "entitlement_quantity": 768.629077
                }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
            "code": 1000016,
            "timestamp": "{ts '2021-01-21 16:42:48'}"
        }
      }
    ```
 
* **Error Response:**

    `code` not supplied
    ```javascript
    __invalid: {
      "code": "field is required"
    }
    ```

    `code` invalid
    ```javascript
    __invalid: {
      "code": "Employee Code is invalid."
    }
    ```

    `code` payroll must be enabled
    ```javascript
    __invalid: {
      "code": "Payroll is not enabled."
    }
    ```
    
* **Sample Parameters:**

  ```javascript
    { 
      "code":"1000016"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=GetLeaveBalances&appcode=DEMOEH&company=10&v=2&token=k2kqIQ7dR8ETO4frke91LcA2VoMANy%2BVAVSE5wyfjC4%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getLeaveBalances">
       <input type="hidden" name="appcode" value="DEMOEH">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">k2kqIQ7dR8ETO4frke91LcA2VoMANy+VAVSE5wyfjC4=</textarea>
    </form>
  ```
