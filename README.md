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
  File "/home/app/templates/index.md.jinja2", line 31, in top-level template code
    | {{ loop.index }} | {% if hl %}![](./assets/{{ service_id }}-favicon.webp) {% endif %}{% if hl %}[__{{ services[service_id].name }}__](https://scrapeway.com{{ url_for('serviceview', service_id=service_id) }}){% else %}[{{ services[service_id].name }}](https://scrapeway.com{{ url_for('serviceview', service_id=service_id) }}){% endif %} | {% if loop.index == 1 %}__{{ run.success|round(1) }}%__{% else %}{{ run.success|round(1) }}%{% endif %} | {% if loop.index == 1 %}__{{ run.duration_avg|round(1) }}s__{% else %}{{ run.duration_avg|round(1) }}s{% endif %} | {% if loop.index == 1 %}__${{ run.cpm_calculated|round(1) }}__{% else %}${{ run.cpm_calculated|round(1) }}{% endif %} |
    ^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/site-packages/jinja2/filters.py", line 1182, in do_round
    return round(value, precision)
           ^^^^^^^^^^^^^^^^^^^^^^^
TypeError: type Undefined doesn't define __round__ method
