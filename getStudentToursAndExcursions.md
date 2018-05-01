**getStudentToursAndExcursions**
----
Retrieve Tours and Excursions basic information based specified on student.

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `studcode [string]` - Student Code
   
   **Optional:**
 
   `client_ip [string IP Address]` - May be required for attachments if proxying the initial request but not the file download

   **Conditional:**

   none

* **Success Response:**
    
    `Status_Code: 200`
    ```javascript
    {
      "data": [
        {
          "tour_url": "http://riverlife.com.au/",
          "tour_when": "Thu 07/12/2017 at 12:30pm (ends 3:30pm)",
          "attachment": {
          "deep_link": "{\"target\":\"tours.attachment\",\"studcode\":\"20114\",\"tour_num\":\"35\",\"prod_menu\":\"Y\"}",
          "file_name": "tours_attachment.pdf"
        },
        "tour_desc": "Rock Climbing Excursion",
        "deep_link": "{\"target\":\"tours.tour\",\"studcode\":\"20114\",\"tour_num\":\"35\",\"prod_menu\":\"Y\"}",
        "tour_num": 35,
        "companyCode": 10,
        "tour_status": "Invited",
        "username": 10040,
        "start": "2017-12-07 12:30:00",
        "end": "2017-12-07 15:30:00"
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
    {"studcode":"20114"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
    https://api.tassweb.com.au/tassweb/api/?authtoken=FABC7B09-CC98-41BA-6CECAE11621AE443&appcode=DEMOAPP&v=2&method=GetStudentToursAndExcursions&authentity=parent&token=%2FDcEGAVJXV%2FZ%2FF%2FxHGcsX4TD5Odppmxb5lv8ogscl%2FQ%3D&company=10
	```
  
* **Sample POST:**

	```HTML
    <form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
      <input type="hidden" name="method" value="getStudentToursAndExcursions">
      <input type="hidden" name="appcode" value="DEMOAPP">
      <input type="hidden" name="company" value="10">
      <input type="hidden" name="v" value="2">
      <textarea name="token">/DcEGAVJXV/Z/F/xHGcsX4TD5Odppmxb5lv8ogscl/Q=</textarea>
      <input type="hidden" name="authtoken" value="FABC7B09-CC98-41BA-6CECAE11621AE443">
      <input type="hidden" name="authentity" value="parent">
    </form>
	```
