**getStudentEDiary**
----
Retrieve Student EDiary feed based on specified student.

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
		{
			"events": [
				{
					"location": "Library",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "Wed 08 Feb 2017 at 12:00am (End 12:00am)",
					"dayFlag": "",
					"summary": "Cupcakes will be selling for $3 outside the library to raise money for the RSPCA.",
					"has_attachment": false,
					"description": "Cupcakes will be selling for $3 outside the library to raise money for the RSPCA.",
					"single_day": true,
					"source": "school",
					"title": "RSPCA Cupcake Day",
					"start": "2017-02-08 00:00:00",
					"end": "2017-02-08 00:00:00",
					"id": 6801,
					"url_link": "",
					"all_day": true,
					"feed": "School Calendar"
				},
				{		
					"location": "School Bus",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr A Johnstone in School Bus",
					"description": "Lesson 7: Science 11.A with Mr A Johnstone",
					"has_attachment": false,
					"single_day": true,
					"source": "timetable",
					"start": "2017-12-01 14:30:00",
					"end": "2017-12-01 15:29:00",
					"title": "Science",
					"id": "timetable_78_7650_5_7_11|A_class",
					"url_link": "",
					"all_day": false,
					"feed": "Timetable"
				},
				{
					"location": "Library",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr A Johnstone (English)",
					"description": "Mr A Johnstone (English)",
					"has_attachment": false,
					"single_day": true,
					"source": "pti",
					"start": "2017-09-14 15:30:00",
					"end": "2017-09-14 15:40:00",
					"title": "2017 Term 3 Parent Teacher Interviews",
					"id": 7108,
					"url_link": "",
					"all_day": false,
					"feed": "PT Interviews"
				},
				{
					"location": "AGC",
					"attachment": {
					"deep_link": "",
					"file_name": ""
					},
					"deep_link": "{\"target\":\"tours.tour\",\"studcode\":\"20114\",\"tour_num\":\"7\",\"prod_menu\":\"Y\"}",
					"url_text": "",
					"day_time_desc": "",
					"summary": "Teacher: Mr A Johnstone",
					"description": "Teacher: Mr A Johnstone",
					"has_attachment": false,
					"single_day": true,
					"source": "tours",
					"title": "Australian Girls Choir Auditions",
					"start": "2017-10-09 10:00:00",
					"end": "2017-10-09 14:00:00",
					"id": 7,
					"url_link": "",
					"all_day": false,
					"feed": "Tours & Excursions"
				},
				{
					"location": "Library",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Pastoral Care Entry on Mon 06 Feb 2017",
					"description": "Pastoral Care Entry on Mon 06 Feb 2017\r\nClass/Curriculum",
					"has_attachment": false,
					"single_day": true,
					"source": "pastoral",
					"title": "Homework Support Group",
					"start": "2017-02-08 07:00:00",
					"end": "2017-02-08 08:30:00",
					"id": 6723,
					"url_link": "",
					"all_day": false,
					"feed": "Pastoral Care"
				},
				{
					"location": "",
					"attachment": {},
					"deep_link": "{\"target\":\"curricular.activity\",\"studcode\":\"20114\",\"activity_assign_id\":\"22015\",\"prod_menu\":\"N\"}",
					"url_text": "Go to this activity.",
					"day_time_desc": "",
					"summary": "English 11 A\nActivity Due: Wed 08 Feb 2017 at 02:30 PM",
					"description": "English 11 A\nActivity Due: Wed 08 Feb 2017 at 02:30 PM",
					"has_attachment": false,
					"single_day": true,
					"source": "activity",
					"start": "2017-02-08 14:30:00",
					"end": "",
					"title": "Reading Task - Week 1",
					"id": "activity-20114-0EB973AC-F703-C00F-CE1E1E515846BA1B-22015",
					"url_link": "",
					"all_day": false,
					"feed": "Curricular Activities"
				},
				{
					"location": "",
					"attachment": {
						"deep_link": "",
						"file_name": ""
					},
					"deep_link": "",
					"url_text": "",
					"day_time_desc": "",
					"summary": "Cello Lessons - Clark, Andrea Gracie Joan",
					"description": "Cello Lessons - Clark, Andrea Gracie Joan",
					"has_attachment": false,
					"single_day": true,
					"source": "extracurricular",
					"title": "Music Practice-Tuning the Instrument - Individual Session 2",
					"start": "2020-01-27 15:00:00",
					"end": "2020-01-27 15:30:00",
					"id": "1D2F849F-D779-ADAC-84B5145702FFCD6F",
					"url_link": "",
					"all_day": false,
					"feed": "ExtraCurricular"
				}
			],
			"token": {
				"timestamp": "{ts '2018-05-01 10:33:40'}",
				"end_date": "01/12/2017",
				"start_date": "01/01/2017",
				"studcode": 20114
			}
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
		https://api.tassweb.com.au/tassweb//api/?authtoken=FABC7B09-CC98-41BA-6CECAE11621AE443&appcode=DEMOAPP&v=2&method=GetStudentEDiary&authentity=parent&token=%2FDcEGAVJXV%2FZ%2FF%2FxHGcsXxW9hwXwU5RiYW9N%2FKXIHhNPwb1h5eaXHemaew0tUGTUMBd6M7y%2Fk86eOuCWpUl1oPc228A2dK8jtjcOff4Mg7k%3D&company=10
	```
	
* **Sample POST:**

	```HTML
		<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
			<input type="hidden" name="method" value="getStudentEDiary">
			<input type="hidden" name="appcode" value="DEMOAPP">
			<input type="hidden" name="company" value="10">
			<input type="hidden" name="v" value="2">
			<textarea name="token">/DcEGAVJXV/Z/F/xHGcsXxW9hwXwU5RiYW9N/KXIHhNPwb1h5eaXHemaew0tUGTUMBd6M7y/k86eOuCWpUl1oPc228A2dK8jtjcOff4Mg7k=</textarea>
			<input type="hidden" name="authtoken" value="FABC7B09-CC98-41BA-6CECAE11621AE443">
			<input type="hidden" name="authentity" value="parent">
		</form>
	```