**getDeepLinkURL**
----
Return a fully qualified Deep Link URL based on the supplied Deep Link JSON packet.

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `deep_link [string]`

   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
    
    `Status_Code: 200`
    ```javascript
    {
		"token": {
			"deep_link": "{\"target\":\"tour\",\"studcode\":\"0009130\",\"tour_num\":\"52\",\"prod_menu\":\"N\"}",
			"timestamp": "{ts '2017-11-24 09:24:11'}"
		},
		"url": "http://api.tasscloud.com.au/parentlounge/login.cfm?go={\"target\":\"tour\",\"studcode\":\"0009130\",\"tour_num\":\"52\",\"prod_menu\":\"N\"}&sso_token=2FF54CE4-04C7-E3E4-5061B5F42972DFC0"
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
    {"deep_link":"{\"target\":\"tours.excursions\",\"studcode\":\"0009130\",\"tour_num\":\"52\",\"prod_menu\":\"N\"}"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getDeepLinkURL&appcode=DEMOAPP&company=10&v=2&token=E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1%2FKyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp%2Bg%3D%3D&authtoken=2B5EFD5C-E9F8-EF28-94FA66492E10A1C9&authentity=parent
	```
  
* **Sample POST:**

	```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="getDeepLinkURL">
      <input type="hidden" name="appcode" value="DEMOAPP">
      <input type="hidden" name="company" value="10">
      <input type="hidden" name="v" value="2">
      <textarea name="token">E6DhrZNz2oXAomF1CG8OIIzti2DNIZOVJBI1/KyH5bEKcgZy6UGNbjnvJAK4cYI7DJDUXQ7YreSFKTCwsJGp+g==</textarea>
      <input type="hidden" name="authtoken" value="2B5EFD5C-E9F8-EF28-94FA66492E10A1C9">
      <input type="hidden" name="authentity" value="parent">
    </form>
	```
