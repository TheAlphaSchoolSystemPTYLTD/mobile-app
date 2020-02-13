**getSchoolCalendar**
----
Retrieve School Calendar feed based on authenticated parent with one or many students.

* **Version History:**

  TASS v50.0.000 - Added campus_code and year_groups to return. (If year_groups is empty object `{}` it is assumed the event belongs to all year groups.

* **Version:**

	2

* **Method:**

	`GET | POST`
	
*  **Params:**

	 **Required:**
 
	 `start_date [date dd/mm/yyyy]`

	 **Optional:**
 
	 `studcode [string]` - student code belonging to the autenticated parent

	 `end_date [date dd/mm/yyyy]` - Defaults to `start_date` if not supplied

	 `client_ip [string IP Address]` - May be required for attachments if proxying the initial request but not the file download

	 `includeparent [bool]` - Defaults to true.  Includes parent calendar events and daily notices

	 `includepublic [bool]` - Defaults to true.  Includes public calendar events and daily notices

	 `includedescriptors [bool]` - Defaults to false.  Includes week descriptor events

	 **Conditional:**

	 none

* **Success Response:**
		
		`Status_Code: 200`
		```javascript
		{"events": [{
			"location": "",
			"attachment": {
				"file_size": 22556,
				"deep_link": "{\"target\":\"calendar.attachment\",\"event_id\":\"6862\"}",
				"file_name": "releasenotes_V47_4_025.pdf"
			},
			"cat_num": 11,
			campus_code: "ARG",
			"url_text": "http://www",
			"day_time_desc": "Wed 25 Oct 2017 at 9:00am (End 3:00pm)",
			"cat_desc": "Academic",
			"dayFlag": "",
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
			"week_descriptor": false,
			"feed": "School Calendar",
			"all_day": false,
			year_groups: {
			    	0: "P",
		    		1: 1,
			    	2: 2,
			    	3: 3,
			    	4: 4,
		    		-1: "PK"
		  	}
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
		{"studcode":"20114","start_date":"01/01/2017","end_date":"01/12/2017"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
		https://api.tassweb.com.au/tassweb/api/?authtoken=FABC7B09-CC98-41BA-6CECAE11621AE443&appcode=DEMOAPP&v=2&method=GetSchoolCalendar&authentity=parent&token=%2FDcEGAVJXV%2FZ%2FF%2FxHGcsXxW9hwXwU5RiYW9N%2FKXIHhNPwb1h5eaXHemaew0tUGTUMBd6M7y%2Fk86eOuCWpUl1oPc228A2dK8jtjcOff4Mg7k%3D&company=10
	```
	
* **Sample POST:**

	```HTML
		<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
			<input type="hidden" name="method" value="getSchoolCalendar">
			<input type="hidden" name="appcode" value="DEMOAPP">
			<input type="hidden" name="company" value="10">
			<input type="hidden" name="v" value="2">
			<textarea name="token">/DcEGAVJXV/Z/F/xHGcsXxW9hwXwU5RiYW9N/KXIHhNPwb1h5eaXHemaew0tUGTUMBd6M7y/k86eOuCWpUl1oPc228A2dK8jtjcOff4Mg7k=</textarea>
			<input type="hidden" name="authtoken" value="FABC7B09-CC98-41BA-6CECAE11621AE443">
			<input type="hidden" name="authentity" value="parent">
		</form>
	```
