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

	 `client_ip [string IP Address]` - May be required for attachments if proxying the initial request but not the file download

	 **Conditional:**

	 none

* **Success Response:**
		
		`Status_Code: 200`
		```javascript
		{"events": [{
			"location": "",
			"attachment": {
				"file_size": 22556,
				"deep_link": "{\"target\":\"calendar.attachment\",\"studcode\":\"20133\",\"event_id\":\"6862\"}",
				"file_name": "releasenotes_V47_4_025.pdf",
				"file_url": "/tassdoc/getFile.cfm?i1=3297D198-E437-03D3-B3FEE8CC67A62B6E&i2=741772D7678647E87570B9B33059CAA1"
			},
			"url_text": "http://www",
			"day_time_desc": "Wed 25 Oct 2017 at 9:00am (End 3:00pm)",
			"dayFlag": "bulletin",
			"summary": "Car wash charity day",
			"has_attachment": true,
			"description": "Car wash charity day",
			"single_day": true,
			"source": "school",
			"title": "Car Wash - Charity day",
			"start": "2017-10-25 09:00:00",
			"end": "2017-10-25 15:00:00",
			"id": 6862,
			"url_link": "http://www",
			"all_day": true
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
		{"end_date":"01/11/2017","start_date":"01/10/2017","studcode":"20133"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
		http://api.tasscloud.com.au/tassweb/api/?authtoken=1C5F8D31-C084-DC2D-7480FBEBA048F334&appcode=DEMOAPP&v=2&method=GetSchoolCalendar&authentity=parent&token=587C1hOG7xIHks3Hpy3%2BFijBb4plHJ5lYG0E563YG4Q7HIEf2Ex%2BuKuzWYR2Ali32XzAcsc5AFSuK5QkRlO1My%2Fy8E%2B1cEVT6UOhKeFwfAU%3D&company=10
	```
	
* **Sample POST:**

	```HTML
		<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
			<input type="hidden" name="method" value="getSchoolCalendar">
			<input type="hidden" name="appcode" value="DEMOAPP">
			<input type="hidden" name="company" value="10">
			<input type="hidden" name="v" value="2">
			<textarea name="token">587C1hOG7xIHks3Hpy3+FijBb4plHJ5lYG0E563YG4Q7HIEf2Ex+uKuzWYR2Ali32XzAcsc5AFSuK5QkRlO1My/y8E+1cEVT6UOhKeFwfAU=</textarea>
			<input type="hidden" name="authtoken" value="1C5F8D31-C084-DC2D-7480FBEBA048F334">
			<input type="hidden" name="authentity" value="parent">
		</form>
	```
