**addEmployee**
----
	Returns "success" and a count of added employee(s), or a structure of invalid validations "__invalid" belonging to employee(s).
	
* **Version History:**

	TASS v51.1 - Method Added

	TASS v57.11 - Added an optional `ceider` parameter.

* **Version:**

	2

* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**

	`salutation_flag [string]` - salutation.

	`surname_text [string]` - surname.

	`given_names_text [string]` - given names.

	`prefer_name_text [string]` - preferred name.

	`initials_text [string]` - initials.

	`start_date [date]` - start date.

	`sex_flag [string]` - gender.

	`status_text [string]` - employeement status.

	`city_text [string]` - town / suburb.

	`add1_text [string]` - address line 1.

	**Conditional:**

	`emp_code [string]` - employee code. Required if Employee Code Format is 'Alpha-numeric'.

	`state_text [string]` - state code. Required if country code is not passed in or passed in as 'AU'.

	`post_code [string]` - post code. Required if country code is not passed in or passed in as 'AU'.

	**Optional:**
	
	`add2_text [string]` - address line 2.

	`phone_h_text [string]` - home phone.

	`phone_w_text [string]` - work phone.

	`marital_stat_flag [string]` - marital status.

	`birth_date [date]` - birth date.

	`driv_lic_text [string]` - driver license.

	`position_text [string]` - position text.

	`nok_name_text [string]` - next of kin name.

	`nok_relat_text [string]` - next of kin relationship.

	`nok_add1_text [string]` - next of kin address line 1.

	`nok_add2_text [string]` - next of kin address line 2.

	`nok_city_text [string]` - next of kin town / suburb.

	`nok_state_text [string]` - next of kin state.

	`nok_post_code [string]` - next of kin post code.

	`nok_country_text [string]` - next of kin country.

	`nok_phone_h_text [string]` - next of kin home phone.

	`nok_phone_w_text [string]` - next of kin work phone.

	`mob_phone [string]` - mobile phone.

	`e_mail [email]` - email.

	`web_password [string]` - Kiosk password.

	`name_suffix [string]` - name suffix.

	`position_title [string]` - position title.

	`vend_code [string]` - supplier code.

	`supervisor_code [string]` - supervisor code.

	`supervisor2_code [string]` - supervisor2 code.

	`sms_flg [string]` - sms flag.

	`school_email [email]` - school email.

	`ceider [string]` - ceider.

* **Success Response:**

	```javascript
		{
			"success": "You successfully saved 1 employee(s).",
			"__tassversion": "01.053.3.000",
			"token": {
					"employee": [
								{
									"salutation_flag": "Dr",
									"web_password": "encrypted",
									"surname_text": "Goo",
									"supervisor_code": 1000075,
									"nok_city_text": "Kelvin Grove",
									"nok_phone_w_text": "0450053333",
									"position_title": "Teacher",
									"supervisor2_code": 1000066,
									"nok_add2_text": "U2 67 Blamey Street",
									"position_text": "teacher",
									"sex_flag": "M",
									"add2_text": "U2 67 Blamey Street",
									"birth_date": "25/06/1986",
									"driv_lic_text": 123456,
									"post_code": 4059,
									"ID": 1,
									"given_names_text": "Jack",
									"nok_post_code": 2589,
									"initials_text": "FG",
									"COUNTRY_TEXT": "",
									"state_text": "QLD",
									"nok_name_text": "Tea",
									"start_date": "25/06/2019",
									"city_text": "KG",
									"emp_code": 9000012,
									"add1_text": "66 Blamey Street",
									"phone_h_text": "0450052002",
									"e_mail": "jack@tass.com",
									"status_text": "P",
									"marital_stat_flag": "S",
									"school_email": "jackschool@tass.com",
									"prefer_name_text": "Jack",
									"nok_phone_h_text": "0450053333",
									"nok_add1_text": "U1 67 Blamey Street",
									"sms_flg": "Y",
									"phone_w_text": "0450052002",
									"nok_state_text": "DID",
									"nok_country_text": "Austria",
									"mob_phone": "0450052002",
									"nok_relat_text": "Mother",
									"name_suffix": "MEE",
									"country_code": "",
									"vend_code": "00012"
								}
					],
					"timestamp": "{ts '2021-01-21 16:32:56'}"
			}
		}
	```
 
* **Error Response:**

	`employee` not supplied
	```javascript
	__invalid: {
		"employee": "'employee' is required."
	}
	```

	`[required_field_name]` not supplied
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"[required_field_name]": "field is required"
			}
		}
	}
	```

	`[field_name]` is not valid
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"[field_name]": "'[field_name]' is not a valid field name."
			}
		}
	}
	```

	`surname_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"surname_text": "exceeds 30 characters."
			}
		}
	}
	```

	`given_names_text` length longer than 40
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"given_names_text": "exceeds 40 characters."
			}
		}
	}
	```

	`emp_code` length longer than 7
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"emp_code": "exceeds 7 characters."
			}
		}
	}
	```
	
	`state_text` length longer than 3
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"state_text": "exceeds 3 characters."
			}
		}
	}
	```

	`post_code` length longer than 10
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"post_code": "exceeds 10 characters."
			}
		}
	}
	```
	
	`country_code` length longer than 2
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"country_code": "exceeds 2 characters."
			}
		}
	}
	```

	`add2_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"add2_text": "exceeds 30 characters."
			}
		}
	}
	```
	
	`phone_h_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"phone_h_text": "exceeds 30 characters."
			}
		}
	}
	```

	`phone_w_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"phone_w_text": "exceeds 30 characters."
			}
		}
	}
	```
	
	`marital_stat_flag` length longer than 1
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"marital_stat_flag": "exceeds 1 characters."
			}
		}
	}
	```

	`driv_lic_text` length longer than 10
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"driv_lic_text": "exceeds 10 characters."
			}
		}
	}
	```
	
	`position_text` length longer than 20
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"position_text": "exceeds 20 characters."
			}
		}
	}
	```

	`nok_name_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_name_text": "exceeds 30 characters."
			}
		}
	}
	```
	
	`nok_relat_text` length longer than 20
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_relat_text": "exceeds 20 characters."
			}
		}
	}
	```

	`nok_add1_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_add1_text": "exceeds 30 characters."
			}
		}
	}
	```
	
	`nok_add2_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_add2_text": "exceeds 30 characters."
			}
		}
	}
	```

	`nok_city_text` length longer than 20
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_city_text": "exceeds 20 characters."
			}
		}
	}
	```
	
	`nok_state_text` length longer than 3
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_state_text": "exceeds 3 characters."
			}
		}
	}
	```

	`nok_post_code` length longer than 10
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_post_code": "exceeds 10 characters."
			}
		}
	}
	```
	
	`nok_country_text` length longer than 20
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_country_text": "exceeds 20 characters."
			}
		}
	}
	```

	`nok_phone_h_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_phone_h_text": "exceeds 30 characters."
			}
		}
	}
	```
	
	`nok_phone_w_text` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"nok_phone_w_text": "exceeds 30 characters."
			}
		}
	}
	```

	`mob_phone` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"mob_phone": "exceeds 30 characters."
			}
		}
	}
	```
	
	`web_password` length longer than 15
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"web_password": "exceeds 15 characters."
			}
		}
	}
	```
	
	`name_suffix` length longer than 30
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"name_suffix": "exceeds 30 characters."
			}
		}
	}
	```

	`position_title` length longer than 100
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"position_title": "exceeds 100 characters."
			}
		}
	}
	```
	
	`vend_code` length longer than 8
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"vend_code": "exceeds 8 characters."
			}
		}
	}
	```

	`supervisor_code` length longer than 7
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"supervisor_code": "exceeds 7 characters."
			}
		}
	}
	```
	
	`supervisor2_code` length longer than 7
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"supervisor2_code": "exceeds 7 characters."
			}
		}
	}
	```

	`sms_flg` length longer than 1
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"sms_flg": "exceeds 1 characters."
			}
		}
	}
	```
	
	`e_mail` length longer than 60
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"e_mail": "exceeds 60 characters."
			}
		}
	}
	```
	
	`school_email` length longer than 60
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"school_email": "exceeds 60 characters."
			}
		}
	}
	```
	
	`start_date` length longer than 10
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"start_date": "exceeds 10 characters."
			}
		}
	}
	```
	
	`birth_date` length longer than 10
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"birth_date": "exceeds 10 characters."
			}
		}
	}
	```
	
	`emp_code` passed in if employee code format is numeric
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"emp_code": "Employee_code not valid when using Numeric Employee Code Format."
			}
		}
	}
	```
	
	`emp_code` if employee code is existed when employee code format is alpha-numeric
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"emp_code": "Employee_code '[emp_code]' has already been used."
			}
		}
	}
	```
	
	`sex_flag` must be M or F
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"sex_flag": "'[sex_flag]' is not a valid gender."
			}
		}
	}
	```
	
	`state_text` must be one of 'QLD,NSW,VIC,TAS,SA,WA,NT,ACT'
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"state_text": "'[state_text]' is not a valid gender."
			}
		}
	}
	```
	
	`state_text` is not passed and country is Australia
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"state_text": "state_text is required if in Australia."
			}
		}
	}
	```
	
	`post_code` must be in the range 0200 to 9999 if stp_enabled = 'Y'
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"post_code": "Post Code must be in the range 0200 to 9999."
			}
		}
	}
	```
	
	`post_code` must be a number if stp_enabled = 'Y'
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"post_code": "Value is not a valid number."
			}
		}
	}
	```
	
	`post_code` is not passed and country is Australia
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"post_code": "post_code is required if in Australia."
			}
		}
	}
	```
	
	`state_text` is passed and country is not Australia
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"state_text": "'[state_text]' is invalid if not in Australia."
			}
		}
	}
	```
	
	`post_code` is passed and country is not Australia
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"post_code": "'[post_code]' is invalid if not in Australia."
			}
		}
	}
	```
	
	`supervisor_code` and `supervisor2_code` must belong to an employee with emp_sort_flag = 'S'
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"supervisor_code": "'[supervisor_code]' is not a valid supervisor code."
			}
		}
	}
	```

	`supervisor2_code` must belong to an employee with emp_sort_flag = 'S'
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"supervisor2_code": "'[supervisor2_code]' is not a valid supervisor code."
			}
		}
	}
	```

	`supervisor2_code` cannot be passed in if supervisor_code is not passed in
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"supervisor2_code": "supervisor2_code is invalid when supervisor_code is undefined."
			}
		}
	}
	```

	`supervisor2_code` cannot be the same as supervisor_code
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"supervisor2_code": "supervisor_code and supervisor2_code cannot be the same."
			}
		}
	}
	```
	
	`status_text` must be a employeement status in table tel_emp_stat
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"status_text": "'[status_text]' is not a valid employeement status."
			}
		}
	}
	```
	
	`country_code` must be a country in table tel_country
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"country_code": "'[country_code]' is not a valid country code."
			}
		}
	}
	```
	
	`marital_stat_flag` must be a marital_stat_flag in table tel_mar_stat
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"marital_stat_flag": "'[marital_stat_flag]' is not a valid marital status flag."
			}
		}
	}
	```
	
	`vend_code` must be a vend_code in table vendor
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"vend_code": "'[vend_code]' is not a valid supplier code."
			}
		}
	}
	```
	
	`sms_flg` must be Y or N
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"sms_flg": "'[sms_flg]' is not a valid sms flag, must be either Y or N."
			}
		}
	}
	```

	`ceider` length longer than 9
	```javascript
	"__invalid": {
		"employee": {
			"[record num]": {
				"ceider": "exceeds 9 characters."
			}
		}
	}
	```


* **Sample Parameters:**

	```javascript
		{
			"employee":
			[
				{
					"salutation_flag":"Dr",
					"surname_text":"Goo",
					"given_names_text":"Jack",
					"prefer_name_text":"Jack",
					"initials_text":"FG",
					"start_date":"25/06/2019",
					"sex_flag":"M",
					"status_text":"P",
					"city_text":"KG",
					"add1_text":"66 Blamey Street",
					"emp_code":"9000012",
					"state_text":"QLD",
					"post_code":"4059",
					"country_code":"AU",
					"add2_text":"U2 67 Blamey Street",
					"phone_h_text":"0450052002",
					"phone_w_text":"0450052002",
					"marital_stat_flag":"S",
					"birth_date":"25/06/1986",
					"driv_lic_text":"123456",
					"position_text":"teacher",
					"nok_name_text":"Tea",
					"nok_relat_text":"Mother",
					"nok_add1_text":"U1 67 Blamey Street",
					"nok_add2_text":"U2 67 Blamey Street",
					"nok_city_text":"Kelvin Grove",
					"nok_state_text":"DID",
					"nok_post_code":"2589",
					"nok_country_text":"Austria",
					"nok_phone_h_text":"0450053333",
					"nok_phone_w_text":"0450053333",
					"mob_phone":"0450052002",
					"e_mail":"jack@tass.com",
					"web_password":"encrypted",
					"name_suffix":"MEE",
					"position_title":"Teacher",
					"vend_code":"00012",
					"supervisor_code":"1000075",
					"supervisor2_code":"1000066",
					"sms_flg":"Y",
					"school_email":"jackschool@tass.com"
				}
			]
		}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=addEmployee&appcode=API013&company=10&v=2&token=BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t%2FKI9ZAFpCMeVXIFlDU5yNQIeYME%2BYLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD%2Bkkt0%2Fuht0suYrSDONP6mx%2Fbt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX%2BraZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE%2FlettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp%2FFr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT%2BltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ%2BinbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb%2BIa0A8%3D
	```
	
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		 <input type="hidden" name="method" value="addEmployee">
		 <input type="hidden" name="appcode" value="API013">
		 <input type="hidden" name="company" value="10">
		 <input type="hidden" name="v" value="2">
		 <textarea name="token">BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t/KI9ZAFpCMeVXIFlDU5yNQIeYME+YLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD+kkt0/uht0suYrSDONP6mx/bt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX+raZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE/lettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp/Fr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT+ltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ+inbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb+Ia0A8=</textarea>
	</form>
	```
