# Linux-On-Samsung-Galaxy-Book-Pro


https://www.intel.com/content/www/us/en/support/articles/000005511/wireless.html

ogesh@yogesh:~/scripts$ cat CB.sh 
#!/bin/sh
CURRBRIGHT=$(xrandr --current --verbose | grep -m 1 'Brightness:')

echo "\n$CURRBRIGHT"

yogesh@yogesh:~/scripts$ cat IB.sh 
#!/bin/sh
CURRBRIGHT=$(xrandr --current --verbose | grep -m 1 'Brightness:' | cut -f2- -d:)

xrandr --output eDP-1 --brightness $(echo "$CURRBRIGHT + 0.1" | bc)


yogesh@yogesh:~/scripts$ cat DB.sh 
#!/bin/sh
CURRBRIGHT=$(xrandr --current --verbose | grep -m 1 'Brightness:' | cut -f2- -d:)

xrandr --output eDP-1 --brightness $(echo "$CURRBRIGHT - 0.1" | bc)
