**getCalendarEvents**
----
Retrieve Calendar Event Categories as a structure.

* **Version:**

	2

* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**
 
	`active [bool]`

	**Optional:**
 
	none

	**Conditional:**

	none

* **Success Response:**
		
	`Status_Code: 200`
	```javascript
	{ 
		"categories": {
			"11": "Academic",
			"22": "School Sections",
			"12": "Staff Events",
			"23": "Medical & Dental Clinic",
			"13": "Art Drama and Music",
			"24": "Miscellaneous",
			"14": "Boarders Events",
			"25": "Week Description"
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
		
		Bool `[field_name]` not a valid bool. `Status_Code: 401`
		```javascript
		__invalid: {
			[field_name]: "Value is not a valid boolean"
		}
		```
		
* **Sample Parameters:**

	```javascript
		{"active":true}
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