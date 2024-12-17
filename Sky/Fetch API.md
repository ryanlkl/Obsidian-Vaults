## Endpoints
### send_request

```Python3
def send_request(payload):
	try:
		response = requests.post(CC_HOST, data=payload, headers=post_headers)
		logger.info(
			"Send metadata request to Clearcast",
			extra={
				"eventType": "AWM_CLEARCAST_FETCH_API",
				"stage": "Make metadata request",
				"response": response,
				"http_latency": response.elapsed.total_seconds() * 1000,
			},
		)

	except Exception as e:
		logger.info(
			"Unable to send request",
			extra={
				"error": e
			}
		)
		raise e

	return response, response.status_code
```

#### What does the function do?

Tries to:

### make_request

``` Python3
def make_request(func, *args):
	retry = 0
	status = -1
	error = None
	response = None

	while return < RETRY_COUNT and status != 200:
		try:
			response, status = func(*args)
				logger.info("Send fetch request to Clearcast",
				extra={
					"eventType": "AWM_CLEARCAST_FETCH_API",
					"stage": "Make fetch request",
					"response": response,
					"status": status,
					"http_latency": response.elapsed.total_seconds() * 1000,
				},
			)
		except Exception as e:
			logger.info(
				"unable to make fetch request",
				extra={
					"eventType": "AWM_CLEARCAST_FETCH_API",
					"stage": "Make fetch request",
					"respnse": response,
					"status": status,
					"error": e,
				},
			)

		if status !=200:
			logger.info(
				"status not 200",
				extra={
					"eventType": "AWM_CLEARCAST_FETCH_API",
					"error": {
							func.__name__
						},
					"retry_count": retry
				},
			)
			time.sleep(2**retry)
			retry += 1
	return response, status, error
```

### invoke_clearcast_api

``` Python3
def invoke_clearcast_api(run_id, last_successful_timestamp=None, apply_delta=True):
	logger.info("cronjob start")
	start_time = datetime.now()
	tdelta = 0
	if apply_delta:
		tdelta = TIME_DELTA

	if not last_sucessful_timestamp:
		_, last_successful_timestamp = datetime.fromtimestamp(time.time() - 900).isoformat(timespec="seconds")
	else:
		last_successful_timestamp = (last_successful_timestamp - timedelta(minutees=tdelta)).isoformat(
			timespec="seconds"
		)

	_, status, error,_
```