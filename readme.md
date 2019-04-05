## About EmailVerify

Steps:

1. Create the MySQL database and write the credentials inside the .env file.
2. php artisan migrate
3. php artisan make:auth
4. In the User.php model, you can see one more contract added called  MustVerifyEmail
5. Add Email Route Verification 
   - Auth::routes(['verify' => true]);
6. Also, we need to protect the HomeController route, so let us do that via adding middleware.
   -   public function __construct()
   -    {
   -        $this->middleware(['auth', 'verified']);
   -    }
7. Setup email configuration
   -    MAIL_DRIVER=smtp
   -    MAIL_HOST=smtp.mailtrap.io
   -    MAIL_PORT=2525
   -    MAIL_USERNAME=null
   -    MAIL_PASSWORD=null
   -    MAIL_ENCRYPTION=null
8. Test the email verification:
   -    http://localhost:8000/register
9. Check the Email and Click on the link 
   -    To verify check the database also and see value of email_verified_at

Laravel is accessible, powerful, and provides tools required for large, robust applications.


## License

The Laravel framework is open-source software licensed under the [MIT license](https://opensource.org/licenses/MIT).
