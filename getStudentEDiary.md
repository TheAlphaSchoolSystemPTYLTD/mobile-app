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
					"location": "",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "Mon 01 Jan 2018 at 9:00am (End 3:00pm)",
					"summary": "Test 34",
					"has_attachment": "NO",
					"description": "Test 34",
					"single_day": "YES",
					"source": "school",
					"title": "Test 34",
					"start": "2018-01-01 09:00:00",
					"end": "2018-01-01 15:00:00",
					"id": 7413,
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "A Block - Room 4",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr A Johnstone in A Block - Room 4",
					"description": "Pastoral Care: Home Room 11.A with Mr A Johnstone",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "timetable",
					"start": "2017-12-01 08:30:00",
					"end": "2017-12-01 09:29:00",
					"title": "Home Room",
					"id": "timetable_80_HOME9997_10_1_11|A_class",
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "B Block - Room 2",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr J Lochlear in B Block - Room 2",
					"description": "Lesson 1: Study of Society & Environment 11.A with Mr J Lochlear",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "timetable",
					"start": "2017-12-01 09:30:00",
					"end": "2017-12-01 10:29:00",
					"title": "Study of Society & Environment",
					"id": "timetable_80_0028_10_2_11|A_class",
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "A Block - Room 1",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr A Johnstone in A Block - Room 1",
					"description": "Lesson 4: Modern History 11.A with Mr A Johnstone",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "timetable",
					"start": "2017-12-01 12:30:00",
					"end": "2017-12-01 13:29:00",
					"title": "Modern History",
					"id": "timetable_80_0021_10_5_11|A_class",
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "Library",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr A Johnstone (Aust. Legal & General Studies)",
					"description": "Mr A Johnstone (Aust. Legal & General Studies)",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "pti",
					"start": "2017-04-25 18:00:00",
					"end": "2017-04-25 18:10:00",
					"title": "Semester 1 2017",
					"id": 88336,
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "Library",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr A Johnstone (English)",
					"description": "Mr A Johnstone (English)",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "pti",
					"start": "2017-04-25 18:10:00",
					"end": "2017-04-25 18:20:00",
					"title": "Semester 1 2017",
					"id": 88337,
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "Library",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"summary": "Mr A Johnstone (Learning Enrichment)",
					"description": "Mr A Johnstone (Learning Enrichment)",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "pti",
					"start": "2017-04-25 18:40:00",
					"end": "2017-04-25 18:50:00",
					"title": "Semester 1 2017",
					"id": 88340,
					"url_link": "",
					"all_day": "NO"
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
					"all_day": false
				},
				{
					"location": "",
					"attachment": {},
					"url_text": "",
					"day_time_desc": "",
					"stud_code": "0009130",
					"summary": "Transport To:  \nTransport From: ",
					"description": "Transport To:  \nTransport From: ",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "leave",
					"title": "Approved Leave - Full Weekend Leave",
					"start": "2017-02-25 14:00:00",
					"end": "2017-02-25 17:00:00",
					"id": 426,
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "",
					"attachment": {},
					"deep_link": "{\"target\":\"curricularactivity\",\"studcode\":\"0009130\",\"activity_assign_id\":\"4434\",\"prod_menu\":\"N\"}",
					"url_text": "Go to this activity.",
					"day_time_desc": "",
					"summary": "English 11 A\nActivity Available From: Wed 23 Aug 2017 at 10:31 AM",
					"description": "English 11 A\nActivity Available From: Wed 23 Aug 2017 at 10:31 AM",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "activity",
					"start": "2017-08-23 10:31:00",
					"end": "",
					"title": "Oral on Captain Corelli's Manodlin",
					"id": "activity-0009130-7D0A8E57-D4F6-ADA4-E76A882402602C5E-4434",
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "",
					"attachment": {},
					"deep_link": "{\"target\":\"curricularactivity\",\"studcode\":\"0009130\",\"activity_assign_id\":\"4443\",\"prod_menu\":\"N\"}",
					"url_text": "Go to this activity.",
					"day_time_desc": "",
					"summary": "Modern History 11 A\nActivity Available From: Sat 01 Jul 2017 at 11:14 AM",
					"description": "Modern History 11 A\nActivity Available From: Sat 01 Jul 2017 at 11:14 AM",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "activity",
					"start": "2017-07-01 11:14:00",
					"end": "",
					"title": "Building the Great Wall Mark 2",
					"id": "activity-0009130-4E12DB9E-E2AD-CBA9-45098D5A848AEC14-4443",
					"url_link": "",
					"all_day": "NO"
				},
				{
					"location": "",
					"attachment": {},
					"deep_link": "{\"target\":\"curricularactivity\",\"studcode\":\"0009130\",\"activity_assign_id\":\"4446\",\"prod_menu\":\"N\"}",
					"url_text": "Go to this activity.",
					"day_time_desc": "",
					"summary": "Modern History 11 A\nActivity Available From: Fri 01 Sep 2017 at 03:17 PM",
					"description": "Modern History 11 A\nActivity Available From: Fri 01 Sep 2017 at 03:17 PM",
					"has_attachment": "NO",
					"single_day": "YES",
					"source": "activity",
					"start": "2017-09-01 15:17:00",
					"end": "",
					"title": "China -",
					"id": "activity-0009130-56BDCCE2-CAD1-1289-5068AEC6098F04E3-4446",
					"url_link": "",
					"all_day": "NO"
				}
			],
			"token": {
				"timestamp": "{ts '2017-11-30 09:45:24'}",
				"end_date": "01/01/2018",
				"start_date": "01/12/2017",
				"studcode": "0009130"
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
		{"studcode":"20071","start_date":"01/01/2017","end_date":"01/12/2017"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
		http://api.tasscloud.com.au/tassweb/api/?method=getStudentEDiary&appcode=DEMOAPP&company=10&v=2&token=E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1%2FKyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp%2Bg%3D%3D&authtoken=2B5EFD5C-E9F8-EF28-94FA66492E10A1C9&authentity=parent
	```
	
* **Sample POST:**

	```HTML
		<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
			<input type="hidden" name="method" value="getStudentEDiary">
			<input type="hidden" name="appcode" value="DEMOAPP">
			<input type="hidden" name="company" value="10">
			<input type="hidden" name="v" value="2">
			<textarea name="token">E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1/KyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp+g==</textarea>
			<input type="hidden" name="authtoken" value="2B5EFD5C-E9F8-EF28-94FA66492E10A1C9">
			<input type="hidden" name="authentity" value="parent">
		</form>
	```