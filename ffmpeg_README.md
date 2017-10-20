ffmpeg for macs can be installed with homebrew

ffmpeg Example:
---------------

`ffmpeg -r 10 -pattern_type glob -i 'comp_*.jpg' -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" -c:v libx264 out.mp4`

-r flag is the framerate
-pattern_type allows for non-numeric ordered files
-c:v is the library for encoding


`ffmpeg -framerate 5 -pattern_type glob -i "*_movie_2015-*.png" -c:v libx264 out.mp4`