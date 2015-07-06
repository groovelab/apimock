# apimock

[![javadoc.io](https://javadocio-badges.herokuapp.com/me.geso.apimock/apimock-core/badge.svg)](https://javadocio-badges.herokuapp.com/me.geso.apimock/apimock-core)

JSON API mock server utilities for Java.

## MOTIVATION

I need to write the JSON API mock server fast!

## SYNOPSIS

    // Create new mock server instance.
		try (APIMockTomcat mock = new APIMockTomcat()) {
      // Register the end point.
			mock.get("/", c -> Collections.emptyMap());
      // Start server instance.
			mock.start();
      // Get the endpoint URI.
			URI uri = mock.getURI();

      // Your test code here.
			HttpResponse resp = Request.Get(uri.resolve("/"))
					.execute()
					.returnResponse();
			assertEquals(200, resp.getStatusLine().getStatusCode());
			assertEquals("{}", EntityUtils.toString(resp.getEntity()));
		}

## Javadoc

 * http://javadoc.io/doc/me.geso.apimock/apimock-core
 * http://javadoc.io/doc/me.geso.apimock/apimock-tomcat

## LICENSE

    The MIT License (MIT)
    Copyright © 2015 Tokuhiro Matsuno, http://64p.org/ <tokuhirom@gmail.com>

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the “Software”), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.

