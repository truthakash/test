
Features:

	* User Registration
	* User Login
	* Forgot password - with password reset email
	* Change password by User
	* Get all User
	* User CRUD 
 
 API Documentation:
 
    1. User Registration:
	      Endpoint	: /accounts/sign_up/
	      Request Type	: POST
	      Params		: username, email, password
        
    2. User Login:
	      Endpoint	: /accounts/sign_in/
	      Request Type	: POST
	      Params		: user_id(username or email), password
	      Response        : { "token": <token> }
        
    3. Forgot Password
	      Endpoint	: /accounts/forget_password/
	      Request Type	: POST
	      Params		: email
	      Request Sample 	: {"email": "some_email_id@gmail.com"}
        
    4. User password link recived from email by above request
	      Endpoint	: /accounts/reset/<reset_code>
	      Request Type	: POST
	      Request Sample 	: {"new_password": "33441122", "new_password_2": "33441122"}
        
    5. Change Password
	      Endpoint	: /accounts/change_password/
	      Request Type	: PUT
	      Request Headers : Authorization : Token <token>
	      Params		: old_password, new_password
        
    6. Get all users
	      Endpoint	: /accounts/user/
	      Request Type	: GET
        
    7. User CRUD
	      Endpoint	: /accounts/user/<pk:to get/update specific user>
	      Request Type	: GET, PUT, DELETE
        
    8. Signout
	      Endpoint	: /accounts/sign_out/
	      Request Type	: DELETE
	      Request Headers : Authorization : Token <token>




Run the project Locally:

	1) Clone the repository.

	2) Go to directory of manage.py and install the requirements.

		pip install -r requirements.txt

		Note: You may configure the virtual environment if required.

	3) Configure email host in setting.py

		EMAIL_HOST_USER = '<to_be_filled>'

		EMAIL_HOST_PASSWORD = '<to_be_filled>'

	Note: By default, Sqlite3 database is used. You may also use different database in settings file if required.
	
	4) Run migrations
		
		python manage.py migrate
	
	5) Ready to run the server.

		python manage.py runserver


Configuration Variables

	SITE_NAME
		
	Name of Website to be displayed on outgoing emails and elsewhere. Defauled is Onboarding POC



