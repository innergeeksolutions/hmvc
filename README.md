# hmvc
CodeIgniter HMVC with frontend and backend modules

Module separation for backend and frontend using wiredesignz HMVC 

I have changed mainly 2 files:
```sh
1. application/config/config.php:

//if PATH_INFO contains admin, then point the modules directory to the backend module
if(isset($_SERVER['PATH_INFO']) && strpos($_SERVER['PATH_INFO'], '/admin') !== false):
  $config['modules_locations'] = array(
    APPPATH.'modules/backend/' => '../modules/backend/',//your backend module directory
  );
else:
  $config['modules_locations'] = array(
    APPPATH.'modules/frontend/' => '../modules/frontend/',//your frontend module directory
  );
endif;

2. application/config/routes.php:

$route['admin'] = "welcome";//default admin controller
$route['admin/(.+)']  = "$1";
```

http://localhost/hmvc for frontend module

and

http://localhost/hmvc/index.php/admin for backend module

application/modules/backend: It is for the backend modules 

application/modules/frontend: it is for the frontend modules


