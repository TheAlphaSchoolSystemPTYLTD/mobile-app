**authenticateParentSSO**
----
Authenticate parent login with SSO, and generates Parent User object with valid Parent session.

* **Version History:**
	
  TASS v52.8 - New endpoint added
	
* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `sso_token [string]`
   
   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
    
    Split Family (`sfa_num` 1 - 9) `Status_Code: 200`
    ```javascript
    {
		"authtoken": "2B5EFD5C-E9F8-EF28-94FA66492E10A1C9",
		"authentity": "parent",
		"loggedin": "YES",
		"par_code": "000011",
		"stud_code": [
			"0009081",
			"0009080"
		],
		"students": [
		{
			"stud_code": "0009080",
			"stud_name": "Paul Angus"
		}, 
		{
			"stud_code": "0009081",
			"stud_name": "Cristine Angus"
		}
		],
		"wasloggedin": "NO",
		"authexpiry": "{ts '2017-11-15 16:57:27'}",
		"par_code_sfa": "000055_1",
		"sfa_num": 1
	}
	```

	Non-Split Family (`sfa_num` 0) `Status_Code: 200`
    ```javascript
    {
		"authtoken": "2B5EFD5C-E9F8-EF28-94FA66492E10A1C9",
		"authentity": "parent",
		"loggedin": "YES",
		"par_code": "000011",
		"stud_code": [
			"0009081",
			"0009080"
		],
		"students": [
		{
			"stud_code": "0009080",
			"stud_name": "Paul Angus"
		}, 
		{
			"stud_code": "0009081",
			"stud_name": "Cristine Angus"
		}
		],
		"wasloggedin": "NO",
		"authexpiry": "{ts '2017-11-15 16:57:27'}",
		"par_code_sfa": "000055_0",
		"sfa_num": 0
	}
	```
 
* **Error Response:**

    Required `[field_name]` not supplied `Status_Code: 401`
    ```javascript
    __invalid: {
      [field_name]: "field is required."
    }
    ```
    
    `[sso_token]` do not match a valid user `Status_Code: 401`
    ```javascript
    __invalid: {
      sso_token: "Incorrect token."
    }
    ```
    
* **Sample Parameters:**

	```javascript
    {"sso_token":""}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=authenticateParentSSO&appcode=DEMOAPP&company=10&v=2&token=ajxcMGXFJgzRrd0FJg54CzXDk2PbYXamyaqEIkC7CyQdgqU58z6OoqupTAYyvqACS6ZgJ3DnNdrGd9xaOMgoKQ%3D%3D
	```
  
* **Sample POST:**

	```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="authenticateParent">
      <input type="hidden" name="appcode" value="DEMOAPP">
      <input type="hidden" name="company" value="10">
      <input type="hidden" name="v" value="2">
      <textarea name="token">ajxcMGXFJgzRrd0FJg54CzXDk2PbYXamyaqEIkC7CyQdgqU58z6OoqupTAYyvqACS6ZgJ3DnNdrGd9xaOMgoKQ==</textarea>
    </form>
	```
