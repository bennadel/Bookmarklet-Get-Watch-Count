
# Bookmarklet: Counting Active $watch() Bindings In AngularJS

by [Ben Nadel][bennadel] (on [Google+][googleplus])

The following is a bookmarklet that will count the number of $watch() bindings on the current
page. Each $watch() binding represents processing overhead that AngularJS will have to execute
during each $digest phase. By cutting down on the number of watchers, you can increase the
performance of your AngularJS application.

__Bookmarklet__: <a href="javascript:alert('Watch Count: '+(function getWatchCount(){for(var e=document.querySelectorAll('.ng-scope'),t=0,r={},n=0;n<e.length;n++){var a=angular.element(e[n]).scope();r.hasOwnProperty(a.$id)||(r[a.$id]=!0,a.$$watchers&&(t+=a.$$watchers.length))}return t})());void(0);">Get $watch() Count</a>

This bookmarklet uses `document.querySelectorAll()`, so it may not work in older browsers. That
said, it does not depend on jQuery - only AngularJS.

_Note_: This is a spin-off of my [blog post, Counting The Number Of Watchers In AngularJS][blogpost].
But, it has been modified to be more generic.

[bennadel]: http://www.bennadel.com
[googleplus]: https://plus.google.com/108976367067760160494?rel=author
[blogpost]: http://www.bennadel.com/blog/2698-counting-the-number-of-watchers-in-angularjs.htm
