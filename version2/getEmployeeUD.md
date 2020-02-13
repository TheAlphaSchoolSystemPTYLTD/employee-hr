**getEmployeeUD**
----
	Returns an array of Employee/HR UD data for a specified employee in JSON format.
	
* **Version History:**

	TASS v50.0 - Method Added

* **Version:**

	2

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`code [integer]` - Employee code                    

   **Optional:**

    `area [integer]` - Area code

	`includelookups [boolean]` - Include lookups

   **Conditional:**

	none

* **Success Response:**

    ```javascript
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
				"2": {
					"id": 2,
					"value": "N",
					"desc": "10 Checklist complet",
					"name": "UD2_DESC"
				},
				"3": {
					"id": 3,
					"value": "Y",
					"desc": "Req Courses complete",
					"name": "UD3_DESC"
				},
				"4": {
					"id": 4,
					"value": "",
					"desc": "",
					"name": "UD4_DESC"
				},
				...
				"10": {
					"id": 10,
					"value": "",
					"desc": "",
					"name": "UD10_DESC"
				},
				"11": {
					"id": 11,
					"value": "AD",
					"lookups": [
						{
							"code": "AD",
							"desc": "Adequate"
						},
						{
							"code": "COM",
							"desc": "Commendable"
						},
						{
							"code": "HC",
							"desc": "Highly Commendable"
						},
						{
							"code": "IA",
							"desc": "Inadequate"
						},
						{
							"code": "OS",
							"desc": "Outstanding"
						}
					],
					"desc": "Performance Index",
					"name": "UD11_DESC"
				},
				...
				"14": {
					"id": 14,
					"value": "DUE",
					"lookups": [
						{
							"code": "COM",
							"desc": "Review Complete"
						},
						{
							"code": "DUE",
							"desc": "Review Due"
						}
					],
					"desc": "Performance Status",
					"name": "UD14_DESC"
				},
				...
				"20": {
					"id": 20,
					"value": "",
					"lookups": [],
					"desc": "",
					"name": "UD20_DESC"
				},
				"21": {
					"id": 21,
					"value": "",
					"desc": "",
					"name": "UD21_DESC"
				},
				...
				"26": {
					"id": 26,
					"value": "",
					"desc": "",
					"name": "UD26_DESC"
				}
			}
		}
	]
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

	Invalid `area` not between 1 and 9.
	```javascript
	"__invalid": {
		"area": "Value must be a valid integer between 1 and 9."
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