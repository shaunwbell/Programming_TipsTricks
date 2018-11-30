ffmpeg for macs can be installed with homebrew

ffmpeg Example:
---------------

`ffmpeg -r 10 -pattern_type glob -i 'comp_*.jpg' -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" -c:v libx264 out.mp4`

-r flag is the framerate
-pattern_type allows for non-numeric ordered files
-c:v is the library for encoding


`ffmpeg -framerate 5 -pattern_type glob -i "*_movie_2015-*.png" -c:v libx264 out.mp4`

***making animated gifs***

```bash
ffmpeg -framerate 1 -pattern_type glob -i '2018*.jpg' video.avi
ffmpeg -i video.avi -pix_fmt rgb24 out.gif
```

** if you want to add captions/labels to each frame you need to do it using ImageMagick and the convert tool.  An example shell script to do so by adding the date from the filename is below.

```bash
#!/bin/bash

# Purpose:
#       Obtain date from filename, format it, and add to image


data_dir=${PWD}


for files in `ls ${data_dir}/`
do
    echo "processing file: ${data_dir}/$files"
    IFS='_' read -r -a array <<< "$files"
    echo "DOY ${array[1]}"
    yyyy="2017"; doy="${array[1]}"; 
    doy2date=$(date -jf %s $(($(date -jf "%F" "$yyyy-01-01" +%s) + ((10#$doy - 1)) * 86400)) +"%F")
    echo $doy2date
    convert ${data_dir}/${files} -gravity SouthWest -pointsize 30 -draw "fill black  text 50,80  '$doy2date'"  ${array[1]}.jpg
done
```

or just label based on filename

```bash
#!/bin/bash

# Purpose:
#       Obtain date from filename, format it, and add to image


data_dir=${PWD}


for files in `ls ${data_dir}/`
do
    echo "processing file: ${data_dir}/$files"

    convert ${data_dir}/${files} -gravity SouthWest -pointsize 30 -draw "fill black  text 50,80  '$files'"  ${files}.jpg
done
```