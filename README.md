# Scarlatti Catalog of Keyboard Sonatas in CSV Format

This repository provides a machine-readable CSV file cataloguing Domenico Scarlatti's
keyboard sonatas, to facilitate further analyses.

## File Format

The manuscripts all contain a `.csv` file containing the following listing information:

- `K` (number): _Kirkpatrick catalog number of the sonata._

   This file also provides the `L` (for Longo), `P` (for Pestelli) and `Cz` (for Czerny)
   index equivalents, for informational purposes — even though those catalogs are deprecated
   or not in use. The file also provides the `Fl` index introduced by Matthew Flannery.

- `Key` (string): _Key in which the sonata is composed._

- `Tempo` (string): _Tempo marking(s), if any, of the sonata or movements of the sonata._

- `Signature` (string): _Time signature(s) of the sonata or movements of the sonata._

   This fields contains the value `¡` for
   4/4 ([common time](https://en.wikipedia.org/wiki/Time_signature#Simple_vs._compound))
   and `¢` for 2/2 ([_alla breve_](https://en.wikipedia.org/wiki/Alla_breve)), otherwise
   the value for this field is a ratio, such as: `2/4`, `3/4`, `3/8`, `6/8`, `12/8`.

### Sonatas with multiple movements
Some sonatas contain multiple movements: These movements can either have the same
key, tempo indication or time signature, or each movement can change these parameters. To encode this:
- When all the movements of a sonata are covered by the same indication (whether of
  key, tempo, or time signature), then the corresponding field only contains that
  single value.

- When the movements may have different indications, then **the corresponding field
  contains a semi-colon separated list**.

Here are a few examples that cover a number of situations:
```csv
K,   L,   P,   CZ,  Key,             Tempo,                                 Signature
...
 88,  36,   8,  — , G  minor,        Grave;Andante moderato;Allegro;Minuet, ¡;3/8;2/4;3/8
 89, 211,  12,  — , D  minor,        Allegro;Grave;Allegro,                 ¡;3/4;3/8
...
202, 498, 173, 110, B♭ major,        Allegro;Allegro;Vivo,                  3/8;6/8;3/8
...
205, S23, 171,  — , F  major,        Vivo,                                  ¢;12/8
...
333, 269, 338,  — , D  major,        Allegro;Allegrissimo,                  ¢
...
459, S14, 167,  — , D minor;D major, Allegro;Presto,                        3/8;¢
```
Indeed:
- Sonatas K. 88, K. 89 and K. 202 are examples of sonatas with multiple movements, each with the same key/mode, but different tempo indications and time signatures;
- Sonata K. 205 is an example of a sonata with different movements that have the same key/mode and tempo indication, but different time signatures;
- Sonata K. 333 is an example of a sonata with different movements that have the same key/mode and time signature, but different tempo indications;
- Sonata K. 459 is an example of a sonata with different movements, and different key/mode, tempo indications and time signatures.


## Sources

- Flannery, Matthew (2004). _A Chronological Order for the Keyboard Sonatas of Domenico Scarlatti (1685-1757)_. The Edwin Mellen Press.
  [ISBN 978-0773463363](https://en.wikipedia.org/wiki/Special:BookSources/978-0773463363).

- Haile, Chris (2014). [Catalogue of sonatas](https://web.archive.org/web/20140203091817/http://www.chrishail.net/catalogue.pdf) from [_Scarlatti Domenico: A new look at the keyboard sonatas of Domenico Scarlatti for people who use both sides of their brain_](https://www.amazon.com/Scarlatti-Domenico-keyboard-sonatas-people-ebook/dp/B072N92R94). ASIN B072N92R94. 

- [Kirkpatrick, Ralph](https://en.wikipedia.org/wiki/Ralph_Kirkpatrick) (1953). [_Domenico Scarlatti_](https://archive.org/details/domenicoscarlatt0000kirk). Princeton University Press. [ISBN 0-691-02708-0](https://en.wikipedia.org/wiki/Special:BookSources/0-691-02708-0).

- Wikipedia contributors. [_Listing of solo keyboard sonatas by Domenico Scarlatti_](https://en.wikipedia.org/wiki/List_of_solo_keyboard_sonatas_by_Domenico_Scarlatti) Wikipedia, The Free Encyclopedia. Wikipedia, The Free Encyclopedia, 20 Jan. 2021. Web. 25 Mar. 2021.

## License

## Acknowledgments

This dataset was curated in the context of a [2020–2021 Dataset Curation
Grant](https://cdh.princeton.edu/projects/computer-assisted-pattern-analysis-domenico-scarlattis-keyboard-sonatas/)
by Princeton University's [Center for Digital Humanities](https://cdh.princeton.edu/).
