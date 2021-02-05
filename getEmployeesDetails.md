**getEmployeesDetails**
----
  Returns an array of structured Employee data comprising general, address, and next of kin details in JSON format.

* **Version History:**

  TASS v48 - Method Added
  
  TASS v49.7.044 - Added optional `includephoto` and `thumbnail` parameters
  
* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `date [date dd/mm/yyyy]` -  Termination Date
   
   **Optional:**

   `code [string]` - Employee code
   
   `includephoto [boolean]` -  Must be 'true' or 'false' for whether returning employee photo.

   **Conditional:**
 
   `thumbnail [boolean]` -  Must be 'true' or 'false' for whether or not to employee thumbnail photo. Only valid where `includephoto` is 'true'

* **Success Response:**

    ```javascript
      {
        "employees": [
              {
                "address": {
                      "town_suburb": "BRISBANE",
                      "address_line_1": "114 Queen Street",
                      "address_barcode": "",
                      "address_description": "1. Employee Address *",
                      "address_line_2": "Bowen Hills",
                      "state": "QLD",
                      "employee_name": "Mr ASJ Johnstone",
                      "email": "AJ333@tassweb.com.au",
                      "work_phone": "123456789 333",
                      "mobile_phone": "0412016500",
                      "country": "",
                      "sms": "Y",
                      "post_code": 4000,
                      "home_phone": "123456789 333"
                },
                "general": {
                      "initials": "ASJ",
                      "employment_status": "F",
                      "surname": "Johnstone",
                      "marital_status": "M",
                      "supervisor": "",
                      "position_title": "Head of Senior School",
                      "start_date": "04/09/2000",
                      "employee_code": 1000016,
                      "school_email": "AJSCHOOL@TASSWEB.COM",
                      "teacher_code": "AJ",
                      "position_text": "Teacher",
                      "termination_date": "",
                      "supervisor_2": "",
                      "preferred_name": "Al",
                      "name_suffixes": "BA, DipTch (MIT), QCT",
                      "gender": "U",
                      "title": "Mr",
                      "driver_licence_no": "X5367",
                      "date_of_birth": "21/06/1968",
                      "supplier_code": "",
                      "given_names": "Alan Fred"
                },
                "next_of_kin": {
                      "town_suburb": "KIPPA RING",
                      "address_line_1": "Borella Circuit",
                      "country": "AU 333",
                      "address_line_2": "",
                      "state": "QLD",
                      "post_code": 4020,
                      "home_phone": "123456789 333",
                      "relationship": "Slave",
                      "work_phone": "123456789 333",
                      "name": "ssdtr"
                }
              }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
            "date": "10/12/2016",
            "code": 1000016,
            "timestamp": "{ts '2021-01-21 16:35:23'}"
        }
      }
    ```
 
* **Error Response:**

    `date` not supplied
    ```javascript
    __invalid: {
      "date": "field is required"
    }
    ```

    `date` not a valid date
    ```javascript
      "date": "date is invalid."
    ```

    `code` invalid
    ```javascript
    __invalid: {
      "code": "Employee Code is invalid."
    }
    ```
    
* **Sample Parameters:**

  ```javascript
    { 
      "date":"10/12/2016",
      "code":"1000016"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=GetEmployeesDetails&appcode=DEMOEH&company=10&v=2&token=rg1uVRBUqrSJ27fqtHDPpS2CYvDiKFEozzjpYTfgqrdyuVVKcJIcCSshy%2Bxdaan%2B
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getEmployeesDetails">
       <input type="hidden" name="appcode" value="DEMOEH">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">rg1uVRBUqrSJ27fqtHDPpS2CYvDiKFEozzjpYTfgqrdyuVVKcJIcCSshy+xdaan+</textarea>
    </form>
  ```
