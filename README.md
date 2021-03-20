# Store-Data-in-Cookies-with-JavaScript
Store Data in Cookies with JavaScript

```javascript
<script type="text/javascript">
        //document.cookie property to create a cookie using JavaScript.
        document.cookie = "name=John Doe";

        //cookie is deleted once the browser is closed. But, you can set an expiry date and time (in UTC time) to make the cookie alive as per your needs.
        document.cookie = "name=John Doe; expires=Wed, 13 Jan 2021 12:00:00 UTC";

        //cookie belongs to the current page. But, you can set a path the cookie belongs to.
        document.cookie = "name=John Doe; expires=Wed, 13 Jan 2021 12:00:00 UTC; path=/";


        //setCookie("nameofthecookie", "value", 5) function helps to create a cookie with a specific name and value using JavaScript.
        function setCookie(name, value, exp_days) {
            var d = new Date();
            d.setTime(d.getTime() + (exp_days * 24 * 60 * 60 * 1000));
            var expires = "expires=" + d.toGMTString();
            document.cookie = name + "=" + value + ";" + expires + ";path=/";
        }

        //getCookie("nameofthevalue") function helps to retrieve the value of a predefined cookie using JavaScript.
        function getCookie(name) {
            var cname = name + "=";
            var decodedCookie = decodeURIComponent(document.cookie);
            var ca = decodedCookie.split(';');
            for (var i = 0; i < ca.length; i++) {
                var c = ca[i];
                while (c.charAt(0) == ' ') {
                    c = c.substring(1);
                }
                if (c.indexOf(cname) == 0) {
                    return c.substring(cname.length, c.length);
                }
            }
            return "";
        }

        //deleteCookie("nameofthecookie") function helps to remove cookie using JavaScript.
        function deleteCookie(name) {
            var d = new Date();
            d.setTime(d.getTime() - (60 * 60 * 1000));
            var expires = "expires=" + d.toGMTString();
            document.cookie = name + "=;" + expires + ";path=/";
        }

    </script>
    ```
