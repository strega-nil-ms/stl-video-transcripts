## STL Video Transcripts

This repo is for people to contribute to editing transcripts of the
STL Open Code Review meetings. Thank you!

### Layout of the Repo

Each video transcript is in its own directory: `transcripts/<yyyy>/<yyyy-mm-dd>`.
There are three files in here:

- `metadata.json`: contains information about the video, including video title,
  description, and links
- `original.vtt`: the original machine-generated transcript. Do not edit this.
- `edited.vtt`: the edited transcript; this is the one you modify.

### `metadata.json`

There are currently four fields in `metadata.json`:

* `"name"`: Should be GH-NNNN (with NNNN being replaced by the number),
  followed by a comma, followed by the actual title of the PR. If this is a part two, put `(part 2)`
  in a parenthetical after the PR number, but before the comma.
  - `"GH-2158 (part 2), Extend memcpy, memmove, and memcmp optimizations"`
  - `"GH-2019, <functional>: Implement invoke_r"`
* `"description"`: Should look something like:
  - `"In this video we review GH-2158: https://github.com/microsoft/STL/pull/2158, titled \"Extend memcpy, memmove and memcmp optimizations\", now on part 2. Part 1 of the code review can be found at https://youtu.be/aQ4isF4f0bY."`,
* `"private-link"`: Will be filled out by maintainers; the link to the unlisted video
* `"public-link"`: Will be filled out by maintainers; the link to the listed video on
  the Microsoft official youtube channel

### Captioning Style

The following rules should be used:

* Remove any `NOTE Confidence` lines
* To denote a period of silence while mouths are moving,
  (for example, if someone forgot to unmute their microphone),
  or for noises or notes, use `[]` brackets:
  ```vtt
  00:00:03.000 --> 00:00:08.290
  [silence]
  ```
  ```vtt
  01:14:59.310 --> 01:15:02.340
  [under breath] thought it was here, _Can_strong_order.
  ```
* If what was said was just completely unintelligible, write
  `[unintelligible]`:
* For greater than, less than, and ampersand symbols,
  use the `&blah;` syntax:
  ```vtt
  00:00:49.370 --> 00:00:52.286
  line, right line 4005 of &lt;xutility&gt;.
  ```
* To denote a new speaker, use two greater than symbols, followed by the given
  name of the person speaking with the first letter capitalized:
  ```vtt
  00:00:10.940 --> 00:00:12.896
  &gt;&gt; Stephan: Cool, hi, welcome back to another
  ```
* For spoken references to code, write in the captions as you would write code;
  for example, if someone says
  "this takes a const ty one ref left and a const ty two ref right", write:
  ```vtt
  01:11:11.022 --> 01:11:14.031
  This takes a const _Ty1&amp; _Left and a const _Ty2&amp; _Right.
  ```
* For unicode characters, enter them as utf-8; for example (that is an ellipsis):
  ```vtt
  01:12:48.350 --> 01:12:50.840
  On line 3…, no, line 700.
  ```
* Use an ellipsis instead of three periods
* Instead of using a hyphen-minus or an em dash, use an en dash to separate thoughts
  or for parentheticals.
  However, for hyphenated words, use a hyphen-minus:
  ```vtt
  01:13:44.380 --> 01:13:46.200
  Argument Dependent – and I don't do this for everything,

  01:13:46.200 --> 01:13:47.864
  like SFINAE, but may as well.

  01:13:47.864 --> 01:13:50.400
  This is also not universally known – Lookup.
  ```

For a complete example, take a look at [2021-09-09](transcripts/2021/2021-09-09/edited.vtt).
