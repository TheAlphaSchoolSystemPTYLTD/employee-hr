**getLeaveBalances**
----
  Returns an array of structured Leave Balances details in JSON format.

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `code [string]` - Employee code
   
   **Optional:**

   none

   **Conditional:**
 
   none

* **Success Response:**

    ```javascript
      "leave_balances": [
        {
          "accrual_code": "SCF",
          "accrual_start_date": "16/09/1995",
          "unit": "Hours",
          "description": "Sick Current Full",
          "quantity_as_at_date": "23/09/2016",
          "entitlement_quantity": 55
        },
        {
          "accrual_code": "SCH",
          "accrual_start_date": "16/09/1995",
          "unit": "Hours",
          "description": "Sick Current Half",
          "quantity_as_at_date": "23/09/2016",
          "entitlement_quantity": 55
        },
        {
          "accrual_code": "SNF",
          "accrual_start_date": "16/09/1995",
          "unit": "Hours",
          "description": "Sick Non-current Full",
          "quantity_as_at_date": "23/09/2016",
          "entitlement_quantity": 385
        },
        {
          "accrual_code": "SNH",
          "accrual_start_date": "16/09/1995",
          "unit": "Hours",
          "description": "Sick Non-current Half",
          "quantity_as_at_date": "23/09/2016",
          "entitlement_quantity": 385
        }
      ]
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
