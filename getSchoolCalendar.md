**getSchoolCalendar**
----
Retrieve School Calendar feed based on specified student.

* **Version:**

	2

* **Method:**

	`GET | POST`
	
*  **Params:**

	 **Required:**
 
	 `studcode [string]`

	 `start_date [date dd/mm/yyyy]`

	 **Optional:**
 
	 `end_date [date dd/mm/yyyy]` - Defaults to `start_date` if not supplied

	 **Conditional:**

	 none

* **Success Response:**
		
		`Status_Code: 200`
		```javascript
		{"events": [{
			"location": "",
			"attachment": {},
			"url_text": "",
			"day_time_desc": "Sun 22 Jan 2017 at 9:00am (End 3:00pm)",
			"summary": "Rippers Day Holiday",
			"has_attachment": "NO",
			"description": "Rippers Day Holiday",
			"single_day": "YES",
			"source": "school",
			"title": "Rippers Day",
			"start": "2017-01-22 09:00:00",
			"end": "2017-01-22 15:00:00",
			"id": 7416,
			"url_link": "",
			"all_day": "NO"
		}]
	}
	```
 
* **Error Response:**

		Required `[field_name]` not supplied. `Status_Code: 401`
		```javascript
		__invalid: {
			[field_name]: "field is required."
		}
		```
		

		Date `[field_name]` not a valid date. `Status_Code: 401`
		```javascript
		__invalid: {
			[field_name]: "Value is not a valid date."
		}
		```
		
* **Sample Parameters:**

	```javascript
		{"studcode":"20071","start_date":"01/01/2017","end_date":"01/12/2017"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
		http://api.tasscloud.com.au/tassweb/api/?method=getSchoolCalendar&appcode=DEMOAPP&company=10&v=2&token=E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1%2FKyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp%2Bg%3D%3D&authtoken=2B5EFD5C-E9F8-EF28-94FA66492E10A1C9&authentity=parent
	```
	
* **Sample POST:**

	```HTML
		<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
			<input type="hidden" name="method" value="getSchoolCalendar">
			<input type="hidden" name="appcode" value="DEMOAPP">
			<input type="hidden" name="company" value="10">
			<input type="hidden" name="v" value="2">
			<textarea name="token">E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1/KyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp+g==</textarea>
			<input type="hidden" name="authtoken" value="2B5EFD5C-E9F8-EF28-94FA66492E10A1C9">
			<input type="hidden" name="authentity" value="parent">
		</form>
	```
