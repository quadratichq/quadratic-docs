---
description: Description of date-time formatting in Quadratic.
---

# Date-time formatting

In Quadratic you can use either preset date-time options or use custom date-time options.&#x20;

## Date-time presets

Date-time presets include the standard formats you'd expect for both date and time.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-09-10 at 12.02.24@2x.png" alt="" width="353"><figcaption></figcaption></figure>

## Custom formatting&#x20;

A very wide range of custom formatting is supported in Quadratic. The table below reflects all available options for custom formatting.&#x20;

| Spec     | Example                          | Description                                                                                                              |
| -------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| %Y       | 2001                             | Gregorian year padded to 4 digits. Support from -262144 to 262143.                                                       |
| %C       | 20                               | Gregorian year divided by 100, zero-padded to 2 digits.                                                                  |
| %y       | 01                               | Gregorian year modulo 100, zero-padded to 2 digits.                                                                      |
| %m       | 07                               | Month number (01-12), zero-padded to 2 digits.                                                                           |
| %b       | Jul                              | Abbreviated month name. Always 3 letters.                                                                                |
| %B       | July                             | Full month name.                                                                                                         |
| %h       | Jul                              | Same as %b                                                                                                               |
| %d       | 08                               | Day number 01-31, zero padded to 2 digits.                                                                               |
| %e       | 8                                | Same as %d but padded.                                                                                                   |
| %a       | Sun                              | Abbreviated weekday name.                                                                                                |
| %A       | Sunday                           | Full weekday name.                                                                                                       |
| %w       | 0                                | Sunday = 0, Monday = 1, etc.                                                                                             |
| %u       | 7                                | Monday = 1, Tuesday = 2, etc.                                                                                            |
| %U       | 28                               | Week number 00-53, zero padded to 2 digits. Week starting with Sunday.                                                   |
| %W       | 27                               | Same as %U, but week 1 starts with Monday instead of Sunday.                                                             |
| %G       | 2001                             | Same as %Y but ISO 8601 year number.                                                                                     |
| %g       | 01                               | Same %y but year number in ISO 8601                                                                                      |
| %V       | 27                               | Same as %U but uses the week number in ISO 8601 week date (01-53).                                                       |
| %j       | 189                              | Day of the year 001-366, zero padded to 3 digits.                                                                        |
| %D       | 07/08/01                         | Month/day/year format. Same as %m/%d/%y.                                                                                 |
| %x       | 07/08/01                         | Same as %D except locale date representation.                                                                            |
| %F       | 2001-07-08                       | Year-month-day format in ISO 8601. Same as %Y-%m-%d.                                                                     |
| %v       | 8-Jul-2001                       | Day-month-year, same as %e-%b-%Y.                                                                                        |
| %H       | 00                               | Hour number 00-23, zero padded to 2 digits.                                                                              |
| %k       | 0                                | Same as %H but space padded. Same as %\_H.                                                                               |
| %I (aye) | 12                               | Hour number in 12 hour clocks 01-12, zero-padded to 2 digits.                                                            |
| %l (el)  | 12                               | Same as %I (aye), but space-padded, same as %\_I (aye).                                                                  |
| %P       | am                               | am or pm in 12-hour clock                                                                                                |
| %p       | AM                               | AM or PM in 12-hour clocks                                                                                               |
| %M       | 34                               | Minute number 00-59, zero padded to 2 digits.                                                                            |
| %S       | 60                               | Second number 00-60, zero-padded to 2 digits.                                                                            |
| %f       | 26490000                         | Number of nanoseconds since last whole second.                                                                           |
| %.f      | .026490                          | Decimal fraction of a second.                                                                                            |
| %.3f     | .026                             | Decimal fraction of a second with a fixed length of 3.                                                                   |
| %.6f     | .026490                          | Decimal fraction of a second with a fixed length of 6.                                                                   |
| %.9f     | .026490000                       | Decimal fraction of a second with a fixed length of 9.                                                                   |
| %3f      | 026                              | Decimal fraction of a second like `%.3f` but without the leading dot.                                                    |
| %6f      | 026490                           | Decimal fraction of a second like `%.6f` but without the leading dot.                                                    |
| %9f      | 026490000                        | Decimal fraction of a second like `%.9f` but without the leading dot.                                                    |
| %R       | 00:34                            | Hour-minute format. Same as `%H:%M`.                                                                                     |
| %T       | 00:34:60                         | Hour-minute-second format. Same as `%H:%M:%S`.                                                                           |
| %X       | 00:34:60                         | Locale’s time representation (e.g., 23:13:48).                                                                           |
| %r       | 12:34:60 AM                      | Locale’s 12 hour clock time. (e.g., 11:11:04 PM). Falls back to `%X` if the locale does not have a 12 hour clock format. |
| %Z       | ACST                             | Local time zone name. Skips all non-whitespace characters during parsing. Identical to `%:z` when formatting.            |
| %z       | +0930                            | Offset from the local time to UTC (with UTC being `+0000`).                                                              |
| %:z      | +09:30                           | Same as `%z` but with a colon.                                                                                           |
| %::z     | +09:30:00                        | Offset from the local time to UTC with seconds.                                                                          |
| %:::z    | +09                              | Offset from the local time to UTC without minutes.                                                                       |
| %#z      | +09                              | _Parsing only:_ Same as `%z` but allows minutes to be missing or present.                                                |
| %c       | Sun Jul 8 00:34:60 2001          | Locale’s date and time (e.g., Thu Mar 3 23:05:25 2005).                                                                  |
| %+       | 2001-07-08T00:34:60.026490+09:30 | ISO 8601 / RFC 3339 date & time format.                                                                                  |
| %s       | 994518299                        | UNIX timestamp, the number of seconds since 1970-01-01 00:00 UTC.                                                        |
| %t       |                                  | Literal tab (\t).                                                                                                        |
| %n       |                                  | Literal newline (\n).                                                                                                    |
| %%       |                                  | Literal percent sign.                                                                                                    |
| %-?      |                                  | Suppresses any padding including spaces and zeroes. (e.g. `%j` = `012`, `%-j` = `12`)                                    |
| %\_?     |                                  | Uses spaces as a padding. (e.g. %j = 012, %\_j = 12)                                                                     |
| %0?      |                                  | Uses zeroes as a padding. (e.g. %e = 9, %0e = 09)                                                                        |
