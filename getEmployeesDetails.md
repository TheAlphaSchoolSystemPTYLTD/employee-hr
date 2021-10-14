**getEmployeesDetails**
----
  Returns an array of structured Employee data comprising general, address, and next of kin details in JSON format.

* **Version History:**

  TASS v48 - Method Added
  
  TASS v49.7.044 - Added optional `includephoto` and `thumbnail` parameters

  TASS v55.3.000 - Added optional `update_on`, `update_on_from` and `update_on_to` parameters
  
* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `date [date dd/mm/yyyy]` -  Termination Date. Results will omit employee records that finished before this date.
   
   **Optional:**

   `code [string]` - Employee code
   
   `includephoto [boolean]` -  Must be 'true' or 'false' for whether returning employee photo.

   `update_on [date dd/mm/yyyy]` - This Will return employees with a Last Updated date that were updated on this date.

   `update_on_to [date dd/mm/yyyy]` - This Will return employees with a Last Updated date up until the date passed in.

   `update_on_from [date dd/mm/yyyy]` - This Will return employees with a Last Updated date from the date in question to the current date or to the `update_on_to` date (if passed in).

   Using both `update_on_from` and `update_on_to` will return employees with a Last Updated date between the date range.

   !> Use `update_on` to return records from a particular date OR `update_on_from` and `update_on_to` to specify a date range.

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
                      "initials": "A",
                      "employment_status": "F",
                      "surname": "Johnstone",
                      "marital_status": "M",
                      "last_update_on": "15/02/2019 05:04:04 PM",
                      "supervisor": 1000007,
                      "position_title": "Head of Senior School",
                      "start_date": "04/09/2000",
                      "employee_code": 1000016,
                      "school_email": "AJohnstone@tassweb.com.au",
                      "teacher_code": "AJ",
                      "position_text": "Teacher",
                      "last_update_by": "ken",
                      "termination_date": "",
                      "supervisor_2": 1000012,
                      "preferred_name": "Alan",
                      "name_suffixes": "",
                      "gender": "M",
                      "title": "Mr",
                      "driver_licence_no": "",
                      "date_of_birth": "01/11/1968",
                      "supplier_code": "",
                      "given_names": "Alan Pierre"
                },
                "next_of_kin": {
                      "town_suburb": "KIPPA RING",
                      "address_line_1": "Borella Circuit",
                      "country": "AU 333",
                      "address_line_2": "",
                      "state": "QLD",
                      "post_code": 4020,
                      "home_phone": "123456789 333",
                      "relationship": "Partner",
                      "work_phone": "123456789 333",
                      "name": "Jane Johnstone"
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
