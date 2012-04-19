# AsyncQueue

[![Build Status](https://secure.travis-ci.org/martinj/node-async-queue.png)](http://travis-ci.org/martinj/node-async-queue)

## Installation
	
	npm install async-queue
	
## Example

	var AsyncQueue = require('async-queue');

	new AsyncQueue(function (err, job) {
		if (err) job.fail(err);
		setTimeout(function () {
			console.log('First job executed')
			job.success();
		}, 500);
	}, function (err, job) {
		console.log('Second job executed');
		job.success();
	}).run();

Output

	First job executed
	Second job executed

## Run Tests

	npm install
	npm test