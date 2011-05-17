A collection of command line CSV utilities.

    npm install -g csvutils

To see available commands and options

    $ csv --help

## Usage

**Peeking**

To quickly see what's in each column

    $ csv peek < input.csv

**Sorting**

Sort the rows by column number `col_no`

    $ csv sort col_no < input.csv

To sort numerically, use the `-n` switch. To output rows in descending order use the `-d` switch

**Uniques**

To output rows with unique `col_no`

    $ csv unique col_no < input.csv

**Extracting a column**

    $ csv extract col_no < input.csv

To extract multiple columns, use `$ csv extract col1 col2 colN < input.csv`

**Distinct Columns**

To see distinct column values from `col_no`

    $ csv extract col_no < input.csv | csv unique

**Adding elements**

To the start of each line

    $ csv unshift element < input.csv

To the end of each line

    $ csv push element < input.csv

**Slicing**

To input a range of lines

    $ csv slice start_line end_line < input.csv

**Inserting an element**

    $ csv insert pos element < input.csv

**Replacing a column**

    $ csv replace pos element < input.csv

**Counting lines**

    $ csv count < input.csv

**Modifying elements**

    $ csv eval col_no <eval> < input.csv

E.g. remove the "," and "%" characters from column 2

    $ csv eval 2 "column.replace(/[,%]/g, '')" < input.csv

If no column number is specified, the first column is `eval`'d.

E.g. extract column 4 and remove non-int chars

    $ csv extract 4 < input.csv | csv eval "column.replace(/[^0-9]/g,'')"

**Ignoring a header line**

Use the `--header` switch.

## LICENSE

Copyright (c) 2010 Chris O'Hara <cohara87@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

