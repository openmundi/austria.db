# Statistics (Stats)


- 9 states (Bundeslaender)

| Bundesland | Bezirke  | dar. Statutar- städte | dar. Bezirke | Gemeinden | dar. Stadt- gemeinden | dar. Markt- gemeinden |
| ---------- | -------- | ------------------- | ------------ | --------- | -------------- | ------------ |
| Burgenland       |  9 |  2                  |  7           |   171     |  13  |  67 |
| Kärnten          | 10 |  2                  |  8           |   132     |  17  |  47 |
| Niederösterreich | 25 |  4                  | 21           |   573     |  76  | 327 |
| Oberösterreich   | 18 |  3                  | 15           |   442     |  32  | 151 |
| Salzburg         |  6 |  1                  |  5           |   119     |  11  |  24 |
| Steiermark       | 13 |  1                  | 12           |   287     |  35  | 121 |
| Tirol            |  9 |  1                  |  8           |   279     |  11  |  20 |
| Vorarlberg       |  4 |  -                  |  4           |    96     |   5  |  11 |
| Wien             |  1 |  1                  |  -           |     1     |   1  |   - |
| Österreich (Total) | 95 | 15                  | 80           | 2 100     | 201  | 768 |

[(Source: Statistik Austria)](http://www.statistik.at/web_de/klassifikationen/regionale_gliederungen/bundeslaender/index.html)


## Scripts

To double check try:

~~~
require 'worlddb/models'

## connect to ./austria.db
WorldDb.connect( adapter: 'sqlite3', database: './austria.db' )

r = WorldDb::CountryReport.new( 'at' )
r.report
~~~

resulting in:

~~~
Country Report for Austria (at), 9 states

Burgenland (b)                        |    0 parts    9 counties  171 munis    8 cities
Niederösterreich (n)                  |    0 parts   25 counties  573 munis    7 cities
Wien (w)                              |    0 parts    0 counties    0 munis    1 cities
Steiermark (st)                       |    0 parts   13 counties  287 munis    4 cities
Kärnten (k)                           |    0 parts   10 counties  132 munis    3 cities
Oberösterreich (o)                    |    0 parts   18 counties  444 munis    6 cities
Salzburg (s)                          |    0 parts    6 counties  119 munis    2 cities
Tirol (t)                             |    0 parts    9 counties  279 munis    1 cities
Vorarlberg (v)                        |    0 parts    4 counties   96 munis    5 cities

Total:    0 parts,   94 counties,   2101 munis,   37 cities
~~~


To double check orte.txt try:

~~~
require 'textutils'

r = TreeReader.from_file( './3--o-oberoesterreich/orte.txt' )
r.check
~~~

resulting in:

~~~
stats:
{1=>1, 2=>18, 3=>444}
checking level 1 - 1 node(s)...
checking level 2 - 18 node(s)...
checking level 3 - 444 node(s)...
~~~
