**setAcknowledgeNotification**
----
Set a Parent Notificaiton to Acknowledged

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `studcode [string]`

   `alert_num [integer]`
   
   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
    
    `Status_Code: 200`
    ```javascript
    {
	"updated": "YES",
	"token": {
		"alert_num": 123,
		"timestamp": "{ts '2017-12-04 10:28:07'}",
		"studcode": "0009130"
		}
	}
	```
 
* **Error Response:**

    Required `[field_name]` not supplied `Status_Code: 401`
    ```javascript
    __invalid: {
      [field_name]: "field is required."
    }
    ```

    Integer `[field_name]` not a valid integer
    ```javascript
    __invalid: {
      [field_name]: "Value is not a valid integer."
    }
    ```
    
* **Sample Parameters:**

	```javascript
    {"studcode":"0009130","alert_num":123}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=setAcknowledgeNotification&appcode=DEMOAPP&company=10&v=2&token=E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1%2FKyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp%2Bg%3D%3D&authtoken=2B5EFD5C-E9F8-EF28-94FA66492E10A1C9&authentity=parent
	```
  
* **Sample POST:**

	```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="setAcknowledgeNotification">
      <input type="hidden" name="appcode" value="DEMOAPP">
      <input type="hidden" name="company" value="10">
      <input type="hidden" name="v" value="2">
      <textarea name="token">E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1/KyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp+g==</textarea>
      <input type="hidden" name="authtoken" value="2B5EFD5C-E9F8-EF28-94FA66492E10A1C9">
      <input type="hidden" name="authentity" value="parent">
    </form>
	```
