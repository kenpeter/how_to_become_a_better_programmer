# How to become a better programmer

Here is a collection of tricks, methodologies, mechanic, craps, or anything you can think of, to become a programmer.


# How to read doc?


## Speed reading
* Chrome plugin 1: https://chrome.google.com/webstore/detail/spreed-speed-read-the-web/ipikiaejjblmdopojhpejjmbedhlibno
* Chrome plugin 2: https://chrome.google.com/webstore/detail/reedy/ihbdojmggkmjbhfflnchljfkgdhokffj?hl=en

## Comprehension


# How to read code?
For example, I want to read, understand and memorise the core idea of the code.

Here is the original code:
https://github.com/badaoyicai/jav-scrapy/blob/master/actress.js#L149

~~~~
// func
// get girl pic
// maskcode
// pic url
// done, callback
function getActressPic(maskCode, picUrl, done) {
	// condi, pic url
	if(picUrl){
		// file_name is mask_code.jpg
		var filename = maskCode + '.jpg';
		// full file path
		// path.join
		// output/xxxx.jpg
		var fileFullPath = path.join(output + "/" + maskCode, filename);
		// file system, access
		// output/xxxx.jpg
		// file system, file_ok
		// callback, error
		fs.access(fileFullPath, fs.F_OK, function(err) {
			// if there is an error
			if (err) {
				// cover file steam
				// file sys, write steam
				// output/xxx.jpg.part, so we can write
				var coverFileStream = fs.createWriteStream(fileFullPath + '.part');
				// default not finish
				var finished = false;
				// request get, pic_url
				request.get(picUrl)
					// request is end
					// callback
					.on('end', function() {
						// request end, but not finished.
						if (!finished) {
							// so we rename output/xxxx.jpg.part to output/xxx.jpg
							fs.renameSync(fileFullPath + '.part', fileFullPath);
							// now finish
							finished = true;
							// console error
							// [xxxx].green + head.yellow, full path
							console.error(('[' + maskCode + ']').green.bold.inverse + '[头像]'.yellow.inverse, fileFullPath);
							return done();
						}
					})
					.on('error', function(err) {
						// on error, func error
						if (!finished) {
							// not finished, force to be finished
							finished = true;
							// console erorr
							// red, yellow
							console.error(('[' + maskCode + ']').red.bold.inverse + '[头像]'.yellow.inverse, err.message.red);
							// count error
							errorCount++;
							// return done
							return done();
						}
					})
					.pipe(coverFileStream);
			} else {
				// else file exist
				console.log(('[' + maskCode + ']').green.bold.inverse + '[头像]'.yellow.inverse, 'file already exists, skip!'.yellow);
				// return done
				return done();
			}
		});
	}else{
		// log, green, yellow, error.yellow
		console.log(('[' + maskCode + ']').green.bold.inverse + '[头像]'.yellow.inverse, ' error'.yellow);
		return done();
	}
}
~~~~

The idea is that:
* Quickly write some your comments. Have to be your own words.
* Close your eye for 1-2 seconds, then playback what you just read.
* Repeat.



## Speed reading code?



# Daily standup
* Everyday, my team will have a standup meeting. We talk about what we did yesterday. What do we learn from them.
* We set specific tasks can be completed before lunch time.
* After lunch, we discuss how we progress and change our goals accordingly.
* We do a final revew before we leave.
* Repeat the same thing next day.

# Pomodoro technique
Pomodoro uses 25 minutes for a cycle and take 5 minutes as a break. I found that 25 minutes is too long. I set my timer
on phone for 10 minutes, then focus on the task. After 10 minutes, if I feels good, I will keep going for another 10 minutes.
If I stuck, I will go out for a walk. I found that 10 minutes is good for myself. e.g. If you get stuck in 10 minutes, you
have to call a timeout like basketbal, think about what you just did, what went wrong, ask yourself questions, ask why, do some review,
then go back and continue your task.

10 minutes can do lots of things if you are used to it. It may be hard at the start, but slowly you will be very fast.

# Read, read, read

# Build, build, Build

# Read daily Horoscope

# Understand a bit of your brain
* https://www.youtube.com/watch?v=vd2dtkMINIw

# Utilize daily Horoscope
