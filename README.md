# Rubricator

## A CLI Ruby script for fabricating Github commit history

Commits are generated over a specified range of dates and saved via the `git commit --date` option. The number of commits on each date can be randomly generated within a range or set to a fixed value.

By default, the script will use a range of 1 to 10 unless options are given.

### An overview:
```
$ ruby rubricator.rb -h

Usage: ruby rubricator.rb --dates start_date end_date [options] ...

Dates must be formatted as M-D-YY

        --dates date1,date2          Starting and ending dates
    -f, --fixed [number]             Keeps commit count a fixed number
    -r, --range [min,max]            Limit to specific min/max values
    -h, --help                       Display help screen
```

Dates must be entered in the format of M-D-YY, ex. 1-17-16.

Commits are saved in a file called "rubrications.md" by default.

### Example usage:

```
$ ruby rubricator.rb --dates 1-17-16,1-31-16 -r 2,8
80 commits written.
```

This generates commits from January 17, 2016 to January 31, 2016 with a range of 2 to 8 commits per day.

Commits must be manually pushed to your Github repo.
