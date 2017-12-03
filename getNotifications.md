**getNotifications**
----
Retrieve parent Notifications and Notification history.

* **Version:**

	2

* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**
 
	`includehistory [bool]`

	**Optional:**
 
	none

	**Conditional:**

	none

* **Success Response:**
		
	`Status_Code: 200`
	```javascript
	{ "notifications": [
		{
		"created_by": "Mr Alanx O'Johnstonex",
		"alert_num": 5285,
		"end_date": "2017-09-15 10:37:00.0",
		"start_date": "2017-09-14 10:37:00.0",
		"par_com_text": "",
		"alert_text": "Testing alert in Parent Lounge responsiveness",
		"view_date_desc": "",
		"stud_code": "0009130",
		"view_date_flg": "N",
		"conduct_time": "",
		"stud_name": "Andy Clark",
		"view_date": "",
  		"conduct_date": ""
    	}
    ]}
	```
 
* **Error Response:**

		Required `[field_name]` not supplied. `Status_Code: 401`
		```javascript
		__invalid: {
			[field_name]: "field is required."
		}
		```
		
		Bool `[field_name]` not a valid bool. `Status_Code: 401`
		```javascript
		__invalid: {
			[field_name]: "Value is not a valid bool."
		}
		```
		
* **Sample Parameters:**

	```javascript
		{"includehistory":true}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
		http://api.tasscloud.com.au/tassweb/api/?method=getNotifications&appcode=DEMOAPP&company=10&v=2&token=E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1%2FKyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp%2Bg%3D%3D&authtoken=2B5EFD5C-E9F8-EF28-94FA66492E10A1C9&authentity=parent
	```
	
* **Sample POST:**

	```HTML
		<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
			<input type="hidden" name="method" value="getNotifications">
			<input type="hidden" name="appcode" value="DEMOAPP">
			<input type="hidden" name="company" value="10">
			<input type="hidden" name="v" value="2">
			<textarea name="token">E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1/KyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp+g==</textarea>
			<input type="hidden" name="authtoken" value="2B5EFD5C-E9F8-EF28-94FA66492E10A1C9">
			<input type="hidden" name="authentity" value="parent">
		</form>
	```