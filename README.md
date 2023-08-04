# traveltime <!-- omit in toc -->

Traveltime calculates the time difference between different time zones. It is useful for calculating flight times.

- [Usage](#usage)
- [Example](#example)
- [Change Log](#change-log)

## Usage

    Usage: traveltime [-dv] dep_time dep_timezone arr_time arr_timezone [+n]

Traveltime requires a minimum of four arguments. Time and time zone of origin, and time and time zone of destination.

Note: It is the time zone that is specified, not the city name.
For example, there is an airport in San Francisco, but specify "America/Los_Angeles" the time zone.
The time zone can be specified in the same way as for [tzdiff](https://github.com/belgianbeer/tzdiff).

If the arrival time is the next day or the day after next, specify +1 or +2 at the end.

If it exceeds 24 hours, set the -d option to display the combination of day and time.

-v option displays traveltime version.

## Example

Flight AF275 departs Narita Airport at 10:35 and arrives at Paris Charles de Gaulle Airport at 18:30.

```
$ traveltime 10:35 Tokyo 18:30 Paris
14:55   Tokyo -> Paris
```

As with [tzdiff](https://github.com/belgianbeer/tzdiff), the time zone name does not need to be a complete name.

```
$ traveltime 10:35 Tok 18:30 Par
America/Paramaribo      Europe/Paris
$ traveltime 10:35 Tok 18:30 Pari
14:55   Tokyo -> Paris
```

Flight DL120 departs Haneda Airport at 4:20pm and arrives at Minneapolis-Saint Paul International Airport at 1:50pm.

```
$ traveltime 4:20pm Tokyo 1:50pm Chicago
11:30   Tokyo -> Chicago
```

Flight JL1 departs San Francisco International Airport at 12:20 and arrives at Haneda Airport at 15:10 the next day. In this case, specify as follows.

```
$ traveltime 12:20 Los_Angeles 15:10 Tokyo +1
10:50   Los_Angeles -> Tokyo
```

In many cases, the calculation can be performed correctly without specifying "+1".

```
$ traveltime 12:20 Los_Angeles 15:10 Tokyo
10:50   Los_Angeles -> Tokyo
```

## Change Log

- 2023-07-31 ver 0.2 Support am/pm and abort in format error (still Alpha)
- 2023-07-25 ver 0.1 Initial release (Alpha quality)
