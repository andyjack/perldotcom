{
   "tags" : [],
   "thumbnail" : "/images/_pub_2012_04_perlunicook-standard-preamble/unicode.jpg",
   "categories" : "unicode",
   "image" : null,
   "title" : "Perl Unicode Cookbook: Match Unicode Grapheme Cluster in Regex",
   "date" : "2012-05-22T06:00:01-08:00",
   "authors" : [
      "tom-christiansen"
   ],
   "draft" : null,
   "slug" : "/pub/2012/05/perlunicook-match-unicode-grapheme-cluster-in-regex.html",
   "description" : "℞ 29: Match Unicode grapheme cluster in regex In the days of ASCII, we spoke of characters and bytes. We saw few differences between them. In the Unicode world, characters are far more than seven bits of data. Far better..."
}



℞ 29: Match Unicode grapheme cluster in regex
---------------------------------------------

In the days of ASCII, we spoke of characters and bytes. We saw few differences between them. In the Unicode world, characters are far more than seven bits of data. Far better to speak of collections of raw bytes and characters—or even Unicode codepoints.

Programmer-visible "characters" are codepoints matched by `/./s`, but user-visible "characters" are graphemes matched by `/\X/`.

That is to say, the `\X` regex metacharacter matches what Unicode calls an "extended grapheme cluster". Where the user may see a single character (such as a consonant with an accent), the Unicode representation may be that consonant plus combining characters plus the accent mark. Use `\X` to match the entire sequence:

     # Find vowel *plus* any combining diacritics,underlining,etc.
     my $nfd = NFD($orig);
     $nfd =~ / (?=[aeiou]) \X /xi

Previous: [℞ 28: Convert non-ASCII Unicode Numerics](/pub/2012/05/perlunicookbook-convert-non-ascii-unicode-numerics.html)

Series Index: [The Standard Preamble](/pub/2012/04/perlunicook-standard-preamble.html)

Next: [℞ 30: Extract by Grapheme Instead of Codepoint (regex)](/pub/2012/05/perlunicookbook-extract-by-grapheme-instead-of-codepoint-regex.html)
