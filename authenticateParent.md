**authenticateParent**
----
Authenticate parent login, and generates Parent User object with vaid Parent session.

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `username [string]`

   `password [string]`
   
   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
    
    Split Family
    ```javascript
    {
		"authtoken": "2B5EFD5C-E9F8-EF28-94FA66492E10A1C9",
		"loggedin": "YES",
		"par_code": "000055",
		"stud_code": [
			"0009946",
			"0009130",
			"0009134"
		],
		"wasloggedin": "NO",
		"authexpiry": "{ts '2017-11-15 16:57:27'}",
		"par_code_sfa": "000055_1",
		"sfa_num": 1
	}
	```

	Non-Split Family (`sfa_num` 0)
    ```javascript
    {
		"authtoken": "2B5EFD5C-E9F8-EF28-94FA66492E10A1C9",
		"loggedin": "YES",
		"par_code": "000055",
		"stud_code": [
			"0009946",
			"0009130",
			"0009134"
		],
		"wasloggedin": "NO",
		"authexpiry": "{ts '2017-11-15 16:57:27'}",
		"par_code_sfa": "000055_0",
		"sfa_num": 0
	}
	```
 
* **Error Response:**

    Required `[field_name]` not supplied
    ```javascript
    __invalid: {
      [field_name]: "field is required."
    }
    ```
    
    `[username]` and `[password]` do not match a valid user
    ```javascript
    __invalid: {
      username: "Incorrect username or password."
    }
    ```
    
* **Sample Parameters:**

	```javascript
    { "username" : "000055" , "password" : "mysecurepassword" }
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=authenticateParent&appcode=DEMOAPP&company=10&v=2&token=E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1%2FKyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp%2Bg%3D%3D
	```
  
* **Sample POST:**

	```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/api/">
      <input type="hidden" name="method" value="authenticateParent">
      <input type="hidden" name="appcode" value="DEMOAPP">
      <input type="hidden" name="company" value="10">
      <input type="hidden" name="v" value="2">
      <textarea name="token">E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1/KyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp+g==</textarea>
    </form>
	```
