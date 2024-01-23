**getEmployeeUDSetup**
----
	Returns a structured of Employee/HR UD Setup data for a specified area in JSON format.
	
* **Version History:**

	TASS v50.0 - Method Added
	
	TASS v57.9 - Expand UD fields up to 40

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
		{
			"area": {
					"code": 1,
					"description": "Performance Appraisals",
					"responsibility": ""
			},
			"ud": [
				{
					"id": 1,
					"trig": "Y",
					"desc": "2010 Review",
					"name": "UD1_DESC"
				},
				{
					"id": 2,
					"trig": "",
					"desc": "10 Checklist complete",
					"name": "UD2_DESC"
				},
				... // 38 items
			],
			"__tassversion": "01.057.9.000",
			"token": {
					"area": 1,
					"includelookups": true,
					"timestamp": "{ts '2022-08-01 10:33:03'}"
			}
		}
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
