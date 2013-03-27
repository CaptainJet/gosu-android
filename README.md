Gosu-Android
============
A Gosu implementation for Adroid devices.

Installation
-----------

### Linux 

`gem install gosu_android`

As with ruboto, place yourselfe in the root directory of your app and execute
`gosu_android -a` or `gosu_android --add` to automatically copy every gosu_android file to your ruboto project.

### Other platforms 


Sadly right now you need to manually copy every file to every ruboto proyect you want to use it.

- Download the sources
- Copy the `lib/gosu_android` folder and the `gosu.rb` to the `proyect_name/src/` folder inside your [ruboto](http://github.com/ruboto/ruboto) proyect.
- Copy the `lib/gosu.java.jar` in the `proyect_name/libs/` folder.
- Place the `res` files in the `proyect_name/res` folder.
- It is very important that you do not copy the `java` files in your proyect folder, they are included for developers only.


General Information
-------------------
* This is still an early effort, so there are a number of features that had not yet been added. 
* There are some known bugs that I hope to fix soon.
* In its current status there are some small changes to Gosu Window initialization, check examples.
* A new object with some basic physics has been added.

Troubleshooting
-------------------
* If you're using Ruboto 0.10.4 or earlier, you may get an error when trying to require the gosu libraries: `(SystemStackError) stack level too deep` in `require 'gosu'`. If this happens:
	* Replace `require 'gosu'` with  `with_large_stack { require 'gosu' }`. If it still doesn't work:
	* Try `with_large_stack(256)
		require 'gosu'
	end`. If it still doesn't work, try again with `512` instead of `256`.
	* Alternatively, update to the latest Ruboto (0.11 or better).
	* Relevant Ruboto issues:
		* https://github.com/ruboto/ruboto/issues/359
		* https://github.com/ruboto/ruboto/issues/375
* When using several audio files double check that all have the same codification or you could get: `E/MediaPlayer(16127): Unable to to create media player`
 	* http://forums.pragprog.com/forums/152/topics/9144
