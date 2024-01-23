**getEmployeeUD**
----
	Returns an array of Employee/HR UD data for a specified employee in JSON format.
	
* **Version History:**

    Version | Description
    --- | --- |
    TASS v59.02 | New V3 API endpoint released.

* **Version:**

    3

* **Permission:**

    Employee/HR > Employees ---UD Areas tab > View

* **Method:**

	`GET | POST`

*  **Parameters:**

    Parameter Name | Type | Mandatory | Notes
    --- | :---: | :---: | --- |
    code | integer | Yes | Employee code.
    area | integer | No | Area code.
    includelookups | boolean | No | Include lookups.
  
* **Success Response:**

    ```javascript
		{
			"areas": [
				{
					"area": {
							"code": 1,
							"description": "Performance Appraisals",
							"responsibility": ""
					},
					"ud": {
							"1": {
								"id": 1,
								"value": "Y",
								"desc": "2010 Review",
								"name": "UD1_DESC"
							},
							...,
							"12": {
									"id": 12,
									"value": "COM",
									"lookups": [
												{
													"code": "AD",
													"desc": "Adequate"
												},
												{
													"code": "COM",
													"desc": "Commendable"
												}
									],
									"desc": "2009 Rating",
									"name": "UD12_DESC"
							},
							...,
							"40": {
								"id": 40,
								"value": "",
								"desc": "",
								"name": "UD40_DESC"
							}
					}
				}
			],
			"__tassversion": "01.057.9.000",
			"token": {
					"code": 1000016,
					"area": 1,
					"includelookups": true,
					"timestamp": "{ts '2022-08-01 10:33:03'}"
			}
		}
    ```
 
* **Error Response:**

    Required `code` not supplied.
	```javascript
	"__invalid": {
		"code": "field is required"
	}
	```

	Integer `area` not a valid integer.
	```javascript
	"__invalid": {
		"area": "Value must be a valid integer."
	}
	```
	
	Bool `includelookups` not a valid bool.
	```javascript
	"__invalid": {
		"includelookups": "Value is not a valid boolean."
	}
	```
    
* **Sample Parameters:**

	```javascript
	{"code":"1000016","area":"1","includelookups":"true"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://api.tassweb.com.au/tassweb/api/?appcode=DEMOEH&v=2&method=GetEmployeeUD&token=fgTf51Dc7NAuUEIk0%2F6TeP8Trg0IPCsVexIVRLjDa0k5e3S0asAAXcye6IRUVoVQpnuR7A6esnW4TNVv7lONlA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetEmployeeUD">
		<input type="hidden" name="appcode" value="DEMOEH">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">fgTf51Dc7NAuUEIk06TeP8Trg0IPCsVexIVRLjDa0k5e3S0asAAXcye6IRUVoVQpnuR7A6esnW4TNVv7lONlA==</textarea>
	</form>
	```
