##Introduction

CodeIgniter Bootstrap kick starts the development process of the web development process by including Twitter Bootstrap into CodeIgniter. It also includes certain libraries such as AWS and Facebook in-case you are developing applications requiring those SDKs. So stop writing the same code over again and start working on your idea.

CodeIgniter Bootstrap follows the path where it lazy loads libraries. Though the project footprint may be large, the memory footprint will still be extremely light. Try not to autoload libraries as it does not follow the CodeIgniter convention (though some libraries do make sense to autoload).

##Requirements

You will need a proper web server that can run PHP 5.0 or higher. I will also suggest using a MySQL database, though you also encouraged to use other libraries that support a better database like MongoDB.

###Built Around Heroku

Everyone likes free hosting, especially one that easily scales. By design, a LAMP stack has a much higher scalability and availability than most technologies. There are some things that have been added to detect Heroku environments.

##Included Libraries

You can load the several libraries included in CodeIgniter-Bootstrap. These libraries can be worked on an extended on through the directory `application/libraries`. You will also need to edit the configuration files for these SDKs, located at `application/config`.

###Amazon Web Services PHP SDK

    $this->load->library('aws');
    $this->aws->load('s3');
    $this->aws->s3->create_object('bucket', array());
  
More information on the actual SDK can by viewed here:
http://docs.amazonwebservices.com/AWSSDKforPHP/latest/

###Facebook PHP SDK

    $this->load->library('fb');
    $this->fb->sdk->get_user();
    
More information on the Facebook SDK is on:
https://github.com/facebook/php-sdk

###MongoDB Library

    $this->load->library('mongo_db');
    $this->mongo_db->where_gte(); // not a finished code
    
View the MongoDB library for CodeIgniter here:
https://github.com/alexbilbie/codeigniter-mongodb-library/tree/v2

##Extended Helper Functions

###URL Helper

The URL Helper extends the current CodeIgniter URL helper. This helper is also auto-loaded.
http://codeigniter.com/user_guide/helpers/url_helper.html

####is_active($uri)

is_active will return true or false based on if the inputted URI is contained in the current URI. The inputted URI does not need to be full. For example `/api/func/` will match `/api/func/1`. This function is useful when needing to call `class="active"` on elements of HTML.

##Styling your CSS and HTML

By convention, you want to write your HTML documents in the views. They are located at `application/views`. In order to load those views, your controller has to then include the view (including the header and footer view).

In order to edit your styles, you should be editing `assets/css/custom.css`. All your images should go into `assets/img/` and your Javascript code should go into `assets/js/custom.js`. By default, `custom.css` and `custom.js` are included in the `view/include/header.php`. You should insert proper lines into this file to include your other resources.
