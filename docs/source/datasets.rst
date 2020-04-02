.. _datasets:

⭐ Table of supported datasets ⭐
=================================

This table is provided as a guide for users to select appropriate datasets. The
list of annotations omits some metadata for brevity, and we document the dataset's
primary annotations only. The number of tracks indicates the number of unique "tracks"
in a dataset, but it may not reflect the actual size or diversity of a dataset,
as tracks can vary greatly in length (from a few seconds to a few minutes),
and may be homogeneous. For specific information about the contents of each dataset,
click the link provided in the "Module" column.

+------------------+---------------------+---------------------+------------------------+----------+
| Module           | Name                | Downloadable?       | Annotation Types       | # Tracks |
+==================+=====================+=====================+========================+==========+
| beatles_         | | The Beatles       | - audio: ❌         | | Beats_, Chords_,     | 180      |
|                  | | Dataset           | - annotations: ✅   | | Sections_, Key_      |          |
+------------------+---------------------+---------------------+------------------------+----------+
| dali_            | DALI                | - audio: Youtube    | | Lyrics_,             | 5358     |
|                  |                     | - annotations: ✅   | | Vocal Notes_         |          |
+------------------+---------------------+---------------------+------------------------+----------+
| gtzan_genre_     | Gtzan-Genre         | - audio: ✅         | Genre_                 | 1000     |
|                  |                     | - annotations: ✅   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| guitarset_       | GuitarSet           | - audio: ✅         | | Beats_, Chords_,     | 360      |
|                  |                     | - annotations: ✅   | | Key_, Notes_, F0_    |          |
+------------------+---------------------+---------------------+------------------------+----------+
| ikala_           | iKala               | - audio: ❌         | Vocal F0_, Lyrics_     | 252      |
|                  |                     | - annotations: ❌   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| medley_solos_db_ | Medley-solos-DB     | - audio: ✅         | `Instrument Labels`_   | 21571    |
|                  |                     | - annotations: ✅   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| medleydb_melody_ | | MedleyDB Melody   | - audio: On Request | Melody_ F0_            | 108      |
|                  | | Subset            | - annotations: ✅   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| medleydb_pitch_  | | MedleyDB Pitch    | - audio: On Request | | F0_ ,                | 103      |
|                  | | Tracking Subset   | - annotations: ✅   | | `Instrument Labels`_ |          |
+------------------+---------------------+---------------------+------------------------+----------+
| orchset_         | Orchset             | - audio: ✅         | Melody_ F0_            | 64       |
|                  |                     | - annotations: ✅   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| rwc_classical_   | RWC Classical       | - audio: ❌         | Beats_, Sections_      | 50       |
|                  |                     | - annotations: ✅   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| rwc_jazz_        | RWC Jazz            | - audio: ❌         | Beats_, Sections_      | 50       |
|                  |                     | - annotations: ✅   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| rwc_popular_     | RWC Pop             | - audio: ❌         | | Beats_, Sections_,   | 100      |
|                  |                     | - annotations: ✅   | | Vocalactivity_,      |          |
|                  |                     |                     | | Chords_              |          |
+------------------+---------------------+---------------------+------------------------+----------+
| salami_          | Salami              | - audio: ❌         | Sections_              | 1359     |
|                  |                     | - annotations: ✅   |                        |          |
+------------------+---------------------+---------------------+------------------------+----------+
| tinysol_         | TinySOL             | - audio: ✅         | | `Instrument Labels`_,| 2913     |
|                  |                     | - annotations: ✅   | | `Playing Technique`_,|          |
|                  |                     |                     | | Notes_               |          |
+------------------+---------------------+---------------------+------------------------+----------+


Annotation Type Descriptions
----------------------------
The table above provides annotation types as a guide for choosing appropriate datasets,
but it is difficult to generically categorize annotation types, as they depend on varying
definitions and their meaning can change depending on the type of music they correspond to.
Here we provide a rough guide to the types in this table, but we **strongly recommend** reading
the dataset specific documentation to ensure the data is as you expect.

.. _Beats:
Beats
^^^^^
Musical beats, typically encoded as sequence of time stamps and corresponding beat positions.
This implicitly includes *downbeat* information (the beginning of a musical measure).

.. _Chords:
Chords
^^^^^^
Musical chords, e.g. as might be played on a guitar. Typically encoded as a sequence of labeled events,
where each event has a start time, end time, and a label. The label taxonomy varies per dataset,
but typically encode a chord's root and its quality, e.g. A:m7 for "A minor 7".

.. _F0:
F0
^^
Musical pitch contours, typically encoded as time series indidcating the musical pitch over time.
The time series typically have evenly spaced time stamps, each with a correspoinding pitch value
which may be encoded in a number of formats/granularities, including midi note numbers and Hertz.

.. _Genre:
Genre
^^^^^
A typically global "tag", indicating the genre of a recording. Note that the concept of genre is highly
subjective and we refer those new to this task to this `article`_.

.. _Instrument Labels:
Instrument Labels
^^^^^^^^^^^^^^^^^
Labels indicating which instrument is present in a musical recording. This may refer to recordings of solo
instruments, or to recordings with multiple instruments. The labels may be global to a recording, or they
may vary over time, indicating the presence/absence of a particular instrument as a time series.

.. _Key:
Key
^^^
Musical key. This can be defined globally for an audio file or as a sequence of events.

.. _Lyrics:
Lyrics
^^^^^^
Lyrics corresponding to the singing voice of the audio. These may be raw text with no time information,
or they may be time-aligned events. They may have varying levels of granularity (paragraph, line, word,
phoneme, character) depending on the dataset.

.. _Melody:
Melody
^^^^^^
The musical melody of a song. Melody has no universal definition and is typically defined per dataset.
It is typically enocoded as F0_ or as Notes_.

.. _Notes:
Notes
^^^^^
Musical note events, typically encoded as sequences of start time, end time, label. The label typically
indicates a musical pitch, which may be in a number of formats/granularities, including midi note numbers,
Hertz, or pitch class.

.. _`Playing Technique`:
Playing Technique
^^^^^^^^^^^^^^^^^
The playing technique used by a particular instrument, for example "Pizzicato". This label may be global
for a given recording or encoded as a sequence of labeled events.

.. _Sections:
Sections
^^^^^^^^
Musical sections, which may be "flat" or "heirarchical", typically encoded by a sequence of
time stamps indicating musical section boundary times. Section annotations sometimes also
include labels for sections, which may indicate repetitions and/or the section type (e.g. Chorus, Verse).

.. _Vocal Activity:
Vocal Activity
^^^^^^^^^^^^^^
A time series or sequence of events indicating when singing voice is present in a recording. This type
of annotation is implicitly available when Vocal F0_ or Vocal Notes_ annotations are available.


.. _article: https://link.springer.com/article/10.1007/s10844-013-0250-y
.. _beatles: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.beatles
.. _dali: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.dali
.. _gtzan_genre: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.gtzan_genre
.. _guitarset: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.guitarset
.. _ikala: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.ikala
.. _medley_solos_db: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.medley_solos_db
.. _medleydb_melody: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.medleydb_melody
.. _medleydb_pitch: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.medleydb_pitch
.. _orchset: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.orchset
.. _rwc_classical: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.rwc_classical
.. _rwc_jazz: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.rwc_jazz
.. _rwc_pop: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.rwc_pop
.. _salami: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.salami
.. _tinysol: https://mirdata.readthedocs.io/en/latest/source/mirdata.html#module-mirdata.tinysol


