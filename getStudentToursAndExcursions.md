**getStudentToursAndExcursions**
----
Retrieve Tours and Excursions basic information based specified on student.

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
    {
      "data": [
        {
          "tour_when": "Mon 01/08/2016 at 12:00pm (ends 3:30pm)",
          "tour_desc": "Ice Skating Excursion",
          "deep_link": "{\"target\":\"tours.tour\",\"studcode\":\"20359\",\"tour_num\":\"26\",\"prod_menu\":\"N\"}",
          "companyCode": 10,
          "tour_status": "Invited",
          "username": 10246,
          "start": "2016-08-01 12:00:00",
          "end": "2016-08-01 15:30:00"
        }
      ]
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
    {"studcode":"20359"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
    http://api.tasscloud.com.au/tassweb//api/?authtoken=19C60347-AFB3-63FB-27F939E222BF1F79&appcode=DEMOAPP&v=2&method=GetStudentToursAndExcursions&authentity=parent&token=AJdGg4%2FGqZeGHvIzVaL5uxk%2FmrULXRAGbJsyYUhZwR4%3D&company=10
	```
  
* **Sample POST:**

	```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="getStudentToursAndExcursions">
      <input type="hidden" name="appcode" value="DEMOAPP">
      <input type="hidden" name="company" value="10">
      <input type="hidden" name="v" value="2">
      <textarea name="token">AJdGg4\/GqZeGHvIzVaL5uxk\/mrULXRAGbJsyYUhZwR4=</textarea>
      <input type="hidden" name="authtoken" value="19C60347-AFB3-63FB-27F939E222BF1F79">
      <input type="hidden" name="authentity" value="parent">
    </form>
	```
