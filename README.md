# jQuery Cookies

This is a small jQuery plugin for handling cookies. I wrote this because all
other cookie plugins I could find where either dead links or to limited for
my taste.

## Examples

	// get cookie
	var name = $.cookie("name");
	if (name === undefined) {
		console.log("cookie not set");
	}
	
	// set cookie
	$.cookie("name","John Smith");

	// get all cookies
	var all_cookies = $.cookie();
	if ("name" in all_cookies) {
		console.log(all_cookies.name);
	}

	// delete cookie
	$.cookie("name",null);

	// keep cookie for 2 days
	$.cookie("name","John Smith",2);

	// keep cookie until a certain date and restrict it to a certain path and domain
	$.cookie("world","exists",new Date(2012,12-1,21),"/path","example.com");

	// set/delete multiple cookies at once
	$.cookie({
		name: "John Smith",
		occupation: null,
		age: {
			value: "30",
			expires: 365,
			secure: true
		}
	});

## Reference

### $.cookie()

Get all cookies as a map.

### $.cookie( name )

Get value of a cookie. If the cookie is not set `undefined` will be returned.

`name` A string denoting the cokkie to get.

### $.cookie( name, value [, expires [, path [, domain [, secure]]]] )

Set or remove a cookie.

`name` A string denoting the cookie to set.

`value` The value to wich the cookie shall be set as a string. You can pass
`null` if you want to delete the cookie.

`expires` The expiration date of the cookie as string or `Date` object or
the number of days in which the cookie will expire (can be negative). If
`false` is passed a expiration date in the very distant future (2000 years)
is used. If not given or `true` is passed the cookie will expire at the end
of the browser session.

`path` A string containing the path of the serve it should be sent to. If
`true` is passed the current path name is used.

`domain` A string containing the domain of the serve it should be sent to.
If `true` is passed the current host is used.

`secure` If `true` the cookie is limited to encrypted transmissions.

Returns `$`.

### $.cookie( name, settings )

Same as above but pass all arguments but the name in a map.

Returns `$`.

### $.cookie( map )

Same as above but set or remove multiple cookies at once. The keys of map the
are the names of the cookies and the values are strings, `null` or settings
like above.

Returns `$`.

## License

Public Domain. But it would be nice if you credit this github repository
as the source somewhere.
