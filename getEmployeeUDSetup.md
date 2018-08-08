**getEmployeeUDSetup**
----
	Returns a structured of Employee/HR UD Setup data for a specified area in JSON format.
	
* **Version History:**

	TASS v50.0 - Method Added

* **Version:**

	2

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`area [integer]` - Area code                    

   **Optional:**

	`includelookups [boolean]` - Include lookups

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    "area": {
		"code": 1,
		"description": "Performance Appraisals",
		"responsibility": ""
	},
	"ud": [
		{
			"id": 1,
			"trig": "",
			"desc": "2010 Review",
			"name": "UD1_DESC"
		},
		{
			"id": 2,
			"trig": "",
			"desc": "10 Checklist complet",
			"name": "UD2_DESC"
		},
		{
			"id": 3,
			"trig": "",
			"desc": "Req Courses complete",
			"name": "UD3_DESC"
		},
		{
			"id": 4,
			"trig": "",
			"desc": "",
			"name": "UD4_DESC"
		},
		...
			{
			"id": 10,
			"trig": "",
			"desc": "",
			"name": "UD10_DESC"
		},
		{
			"id": 11,
			"trig": "",
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
		{
			"id": 14,
			"trig": "",
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
		{
			"id": 20,
			"trig": "",
			"lookups": [],
			"desc": "",
			"name": "UD20_DESC"
		},
		{
			"id": 21,
			"trig": "",
			"desc": "",
			"name": "UD21_DESC"
		},
		...
		{
			"id": 26,
			"trig": "",
			"desc": "",
			"name": "UD26_DESC"
		}
	]
    ```
 
* **Error Response:**

    Required `area` not supplied.
	```javascript
	"__invalid": {
		"area": "field is required"
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
	{"area":"1","includelookups":"true"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://api.tassweb.com.au/tassweb/api/?appcode=DEMOEH&v=2&method=GetEmployeeUDSetup&token=4DLTBTzaOM7gFofZXpmEQ96oPie%2BNHUnJK1yZ1ZzQ%2Bv%2Bp5M7d8Xs4uvKdS3%2FUCrs&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetEmployeeUDSetup">
		<input type="hidden" name="appcode" value="DEMOEH">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">4DLTBTzaOM7gFofZXpmEQ96oPie+NHUnJK1yZ1ZzQ+v+p5M7d8Xs4uvKdS3UCrs</textarea>
	</form>
	```