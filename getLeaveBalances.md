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
        ???????
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
    http://api.tasscloud.com.au/tassweb/api/?method=getLeaveBalances&appcode=DEMOEH&company=10&v=2&token=???????
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/api/">
       <input type="hidden" name="method" value="getLeaveBalances">
       <input type="hidden" name="appcode" value="DEMOEH">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">???????</textarea>
    </form>
  ```