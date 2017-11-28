**getStudentToursAndExcursions**
----
Authenticate parent login, and generates Parent User object with vaid Parent session.

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `studcode [string]`
   
   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
    
    `Status_Code: 200`
    ```javascript
    {"data": [
		{
			"tour_when": "Wed 13/06/2018 at 9:00am (ends 11:00am)",
			"tour_desc": "Mountain Bike Tour Term 2",
			"deep_link": "{\"target\":\"tour\",\"studcode\":\"0009130\",\"tour_num\":\"52\",\"prod_menu\":\"N\"}",
			"companyCode": 10,
			"tour_status": "Invited",
			"username": "000055"
		},
		{
			"tour_when": "Thu 03/05/2012 at 9:00am (ends 3:00pm)",
			"tour_desc": "Planetarium Excursion",
			"deep_link": "{\"target\":\"tour\",\"studcode\":\"0009130\",\"tour_num\":\"8\",\"prod_menu\":\"N\"}",
			"companyCode": 10,
			"tour_status": "Accepted",
			"username": "000055"
		}]
	}
	```
 
* **Error Response:**

    Required `[field_name]` not supplied `Status_Code: 401`
    ```javascript
    __invalid: {
      [field_name]: "field is required."
    }
    ```
    
* **Sample Parameters:**

	```javascript
    {"studcode":"0009130"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getStudentToursAndExcursions&appcode=DEMOAPP&company=10&v=2&token=E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1%2FKyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp%2Bg%3D%3D&authtoken=2B5EFD5C-E9F8-EF28-94FA66492E10A1C9&authentity=parent
	```
  
* **Sample POST:**

	```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="getStudentToursAndExcursions">
      <input type="hidden" name="appcode" value="DEMOAPP">
      <input type="hidden" name="company" value="10">
      <input type="hidden" name="v" value="2">
      <textarea name="token">E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1/KyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp+g==</textarea>
      <input type="hidden" name="authtoken" value="2B5EFD5C-E9F8-EF28-94FA66492E10A1C9">
      <input type="hidden" name="authentity" value="parent">
    </form>
	```
