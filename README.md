# VTrim
This is a simple Bash command line script that allows you to trim the first n1 and the last n2 seconds from a given video source.

Operation should be lossless, and very performant - as the operations do not transcode the video or audio source there is no loss of quality. On my mid-2012 MacBook Air assets process at approx 450x actual duration.

Requires
--------
Assumes availability of `ffmpeg` and `ffprobe` in the same directory. Users do not need to be familiar with their operation, but should simply install the latest static build from [FFMPEG.org](http://ffmpeg.org)

Usage
-----

`vtrim input-file n1 n2 [output-file]`

- `input-file`: this is the name of the source file
- `n1`: initial trim point in seconds (can be in the format 1*60+14 for one minute and 14 seconds)
- `n2`: number of seconds to trim off the end
- `output-file`: you can optionaly specify the output file name. If not specified then it will take the input filename and make some changes (' - ' becomes '-' and spaces become underscores), and if the filename is the same as the input name, the script will rename the input and add 'in_' to the front.

Notes
-----
- While no transcoding takes place is the input and output file types match (eg mp4 to mp4, or mkv to mkv) if you make a change (eg mp4 to mkv) it will apply a conversion using default ffmpeg settings which will take much longer and will probably not give optimal results.
- If ffmpeg and ffprobe are in a different directory (depends on install method), paths should be adjusted in the script to accomodate

---

To-Do
-----

- Resiliance: make code more able to handle errors (especially when ffmpeg or ffprobe are not present)
- Add support for removing chapters that have a specific metatdata tag (eg 'advertisment')


---

If you make use of this and like it and want to give something back... [I wrote a book!](http://amzn.to/1SHjbLI) :)

Contribute
----------
This project can be forked from
[Github](https://github.com/Offbeatmammal/shVTrim. Please issue pull
requests from feature branches.

License
-------
See Licence file in repo, or refer to http://unlicense.org