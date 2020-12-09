### JQuery-Cookie
This is a simple JQuery plugin that helps to simplify cookie operations. JQuery is required for this library to work

It supports the following operations

- Add a new cookie
  ```javascript
    $.cookie.add(name, value, expires, path, domain, secure)
    $.cookie.add(cookie)
      // cookie is an instance of class Cookie
  ```

- Delete a cookie 
  ```javascript
    $.cookie.delete(name, path, domain, secure)
    $.cookie.delete(cookie)
  ```

- Get a cookie by name or get all cookies if name is not provided
  ```javascript
    $.get(name)
    $.get()
  ```

- Check if a cookie exists by its name
  ```javascript
    $.exist(name)
  ```
  
See [JQuery-Cookie examples](test.html) for more details on how to use this library
  ```javascript
  var thirtyDaysInSecond = 30 * 24 * 3600;
  $('#btnCookie1').click(function () {
      $.cookie.add(new Cookie('username', 'hoaftq', thirtyDaysInSecond, '/'));
  });

  $('#btnCookie2').click(function () {
      $.cookie.add('password', 'Password', thirtyDaysInSecond, '/');
  });

  $('#btnShowCookies').click(function () {
      alert(JSON.stringify($.cookie.get()));
  });

  $('#btnShowCookie1').click(function () {
      alert($.cookie.get('username'));
  });

  $('#btnDelCookie1').click(function () {
      $.cookie.del('username', '/');
  });

  $('#btnDelCookie2').click(function () {
      $.cookie.del('password', '/');
  });

  $('#btnExistCookie2').click(function () {
      if ($.cookie.exist('password')) {
          alert('Cookie2 exists');
      } else {
          alert('Cookie2 does not exist');
      }
  });
  ```
  
The [248Game repository](https://github.com/hoaftq/248Game/blob/master/controller.js) also uses this library to store the highest score locally
