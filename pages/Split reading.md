title: Split reading
id: splitreading
type: subpage
ankiweb_id: 3100585138
parent: Download audio

Use the standard add-ons when learning Japanese or Chinese.

## Japanese

When learning Japanese, using this add-on is much easier when the
[Japanese Support](https://ankiweb.net/shared/info/3918629684) add-on
has been installed first.

This add-on assumes that there is a field called “Reading” and that
this reading field contains both the Japanese word itself (kanj and
kana written in line) and the reading of the kanji (furigana).  The
furigana should be in square brackets
(“[\[](http://www.fileformat.info/info/unicode/char/5b/index.htm)”,
“[\]](http://www.fileformat.info/info/unicode/char/5d/index.htm)”)
after the kanji. A
[space](http://www.fileformat.info/info/unicode/char/20/index.htm) is
used as the break between leading characters and the kanji for which
there is a reading. For example, for the expression「この間」, the
reading field should contain 「`この 間[あいだ]`」.  Note the space
between 「の」 and 「間」 and the square brackets around the 「あいだ」.

Most of the time these details are not important. This square-bracket
style is exactly what is porduced by the Japanese Support add-on. When
creating cards you typically just type the expression into its field,
and when you go to the meaning field to type the translation, the
reading field is filled automatically in the right format.


## Using two fields

Some people store just the kana in the “Reading” field, for example by
using `%r` instead of `%e[%r]` to fill the field in the settings of
the [Yomichan](https://ankiweb.net/shared/info/934748696) add-on.
With this set-up, downloads from Japanesepod will not work without
change. By default the add-on expects to find the kanji in the reading
field.

<figure>
<img src="images/update_kanji_kana.png" alt="Anki Download audio dialog
window. Text: Requestst send to the download sites. Reading. Edit texts:
夫 おっと, Text: Expression. Edit text 夫.">
<figcaption>Kanji and kana in different edit fields.</figcaption>
</figure>
Set the `meaning_in_reading_field` switch to `False` in the
[`get_fields.py`](https://github.com/ospalh/anki-addons/blob/master/downloadaudio/get_fields.py#L45)
file when you use this set-up. With this the Japanesepod downloader
takes the kanji and kana from separate fields. Check with the “Manual
audio” menu item, there should be a line with two edit fields and the
kanji in the left and the kana in the right field.