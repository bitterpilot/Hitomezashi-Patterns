# main flow

set length to line length
set list as a list of coordinates with initial value of [(0,0), (0,length)].

## map polygon

```plaintext
start a loop
set currentCoordinate to list[-1].

    check for other lines at currentCoordinate.
        if there are 2 then one was the one you just traversed.
          traverse the other one.
          add other end of line to list.
          register line as visited
        else if there are 3
          A 3 point intersection will only happen on the border
          Choose the path that takes you away from the border
          add other end of line to list.
          register line as visited
          <!-- TODO: what happens when you come in from the middle and meet the edge? -->

        check that currentCorodinate is not = to list[0] i,e first coordinate
        if equal then close the polygon.
        else continue loop.
```

## draw function

```plaintext
set columns number from user input
set rows = to columns

get window width

set linelength
    # line length should not be less than 20 or more than 50.
    if width / columns > 50
        linelength = 50
    else if width / columns < 20
        linelength = 20
    else
        linelength = width / columns rounded to the nearest integer

for each column
    set shifted as bool from user

    set i = 0 # we want to start at zero so when drawing the first line we get one next to the border.
    set x = to linelength # this spaces it out from the left border
    for each row
        if shifted is true
            increment i to move it away from the top border
            startpoint( x , y = i * length)
            endpoint( x , y = i + 1  * length)

        else
            startpoint( x , y = i * length)
            endpoint( x , y = i + 1  * length)

        increment i

```
