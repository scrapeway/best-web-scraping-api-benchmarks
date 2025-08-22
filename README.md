Traceback (most recent call last):
  File "/usr/local/lib/python3.12/site-packages/litestar/middleware/_internal/exceptions/middleware.py", line 158, in __call__
    await self.app(scope, receive, capture_response_started)
  File "/usr/local/lib/python3.12/site-packages/litestar/routes/http.py", line 81, in handle
    response = await self._get_response_for_request(
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/litestar/routes/http.py", line 133, in _get_response_for_request
    return await self._call_handler_function(
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/litestar/routes/http.py", line 184, in _call_handler_function
    return await route_handler.to_response(app=scope["litestar_app"], data=response_data, request=request)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/litestar/handlers/http_handlers/base.py", line 584, in to_response
    return await response_handler(app=app, data=data, request=request)  # type: ignore[call-arg]
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/litestar/handlers/http_handlers/_utils.py", line 152, in handler
    return response.to_asgi_response(  # type: ignore[no-any-return]
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/litestar/response/template.py", line 149, in to_asgi_response
    body = template.render(**context).encode(self.encoding)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/jinja2/environment.py", line 1295, in render
    self.environment.handle_exception()
  File "/usr/local/lib/python3.12/site-packages/jinja2/environment.py", line 942, in handle_exception
    raise rewrite_traceback_stack(source=source)
  File "/home/app/templates/index.md.jinja2", line 18, in top-level template code
    ## {{ target.primary_domain }} web scraping benchmarks
    ^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/jinja2/environment.py", line 490, in getattr
    return getattr(obj, attribute)
           ^^^^^^^^^^^^^^^^^^^^^^^
jinja2.exceptions.UndefinedError: 'dict object' has no attribute 'antifingerprint'
