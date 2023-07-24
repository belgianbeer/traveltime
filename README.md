# traveltime

Traveltime calculates the time difference between different time zones. It is useful for calculating flight times.


## Usage

    Usage: traveltime [-d] dep_time dep_timezone arr_time arr_timezone [+n]

Traveltime requires a minimum of four arguments. Time and time zone of origin, and time and time zone of destination. Note that it is the time zone that is specified, not the city name. For example, there is an airport in San Francisco, but you would specify Los Angeles as the time zone.

If the arrival time is the next day or the day after next, specify +1 or +2 at the end.

If it exceeds 24 hours, set the -d option to display the combination of day and time.

## Example

Flight JL1 departs San Francisco at 12:20 and arrives at Haneda at 15:10 the next day. In this case, specify as follows.

```
$ traveltime 12:20 Los_Angeles 15:10 Tokyo +1
10:50   Los_Angeles -> Tokyo
$ 
```

Flight AF275 departs Narita airport at 10:35 and arrives at CDG at 18:30. In this case, specify as follows.

```
$ traveltime 10:35 Tokyo 18:30 Paris
14:55   Tokyo -> Paris
$ 
```
