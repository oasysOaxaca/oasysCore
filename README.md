# oasyscore

## Build & development

Run `grunt` for building and `grunt serve` for preview.


Add a `<script>` to your `index.html`:

```html
<script src="/bower_components/angular/oasyscore.js"></script>
<script src="bower_components/ng-file-upload/angular-file-upload.js"></script>

#Configure in your app

Add

Default configuration is enabled

create JSON file whit next content:

{ "transaction": "OK",
    "object": {
        "id": 1,
        "username": "guest@nip.com.mx",
        "role": "guest"
    }
}

save de file whit extenxion .jso for example user.json

create JSON filo whith next content :

{ "transaction": "OK",
    "object": {
        "uris":["/newsDetails","/work","/news","/course"],
        "redirect":"login"
    }
}
save de file whit extenxion .jso for example uri.json

put this files into new folder on our base path of server.

Put this variables into module js.
```html
/*configuration for  guest user service*/
var guestRequestApi = {
    url:"./api/user.json",//dir of file was configured above
    contentType: 'application/json',//application/x-www-form-urlencoded
    method:'GET',
    appName :"default"
};
//configuration for login
var loginConfig ={
    method :"POST",
    contentType: "application/x-www-form-urlencoded",
    transformRequestData: true
};
var autenticationConfig = {
    guestRequestApi:guestRequestApi,
    login:loginConfig
};

angular.module('oasyscore').value('apiUrl',"")
    .constant("autenticationConfig",autenticationConfig)

Configure Route for loading

$routeProvider
      .when('/loading', {
          templateUrl: 'views/core/loading.html',//your view path, and yor view while page loading
          controller: 'LoadingController' // this name cotroller exist in the core, not need implementation
      });






