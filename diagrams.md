
# Table of Contents

1.  [Creating simple process diagrams in Emacs (diary entry?)](#org38acea2)
2.  [Emacs Artist mode](#org9dcc862)
    1.  [Installation](#orgbff7ca3)
        1.  [Drawing a poly-line](#orgd3ff5bb)
    2.  [ascii-art-to-unicode](#org6c199b2)
3.  [Org Tables](#org02daa3d)
4.  [PlantUML](#org67f4383)
5.  [References](#orgd9ae914)


<a id="org38acea2"></a>

# Creating simple process diagrams in Emacs (diary entry?)

I needed this because I wanted to make a simple diagram. Usually, I
would have drawn this in Signavio, or in PowerPoint, made a
screenshot, saved it and embedded it in the Org-file using Emacs. 4
steps, 4 softwares, and not much to show for it.

Since I like to do everything in Emacs using the keyboard, I was
curious if this can be done using ASCII, without extra tools. I
found two ways (in fact, there is a third one, Emacs `artist` mode
(built into Emacs) and `ditaa` (which is no longer distributed with
Org).

1.  [Poor man's UML / Emacs Artist Mode](https://robrohan.com/2015/01/17/poor-mans-uml-artist-mode.html) (Rohan, 2015)
2.  [Generating simple process diagrams using dot and tables](https://orgmode.org/worg/org-tutorials/org-dot-diagrams.html)
3.  [PlantUML and Emacs](https://plantuml.com/emacs) - wrapper to [GraphViz](http://www.graphviz.org/)


<a id="org9dcc862"></a>

# Emacs Artist mode

> "Most people that see me using it either think it’s the most
> ridiculous thing they’ve seen, or they think it’s the coolest thing
> since sliced bread."

I side with those who think it's cool. Tried this first a couple of
years back when I returned to Emacs but haven't used it since.

There is a video demo (13 min) at the end Rohan's blog post. Here,
I'm going to retrace the demo and aim at creating my own simple
diagram at the end.

To make the ASCII art into image files, Rohan suggests [`ditaa`](http://ditaa.sourceforge.net/),
which apparently was bundled with Org in the past, but is no longer
bundled with it.


<a id="orgbff7ca3"></a>

## Installation

`artist` mode is built in.

> "Artist is an Emacs lisp package that allows you to draw lines,
> rectangles, squares, poly-lines, ellipses and circles by using your
> mouse and/or keyboard. The shapes are made up with the ascii
> characters |, -, / and \\."  ([Source: EmacsWiki](https://www.emacswiki.org/emacs/ArtistMode))


<a id="orgd3ff5bb"></a>

### Drawing a poly-line

    M-x artist-mode RET
    C-c C-a p RET
    RET

──────f
      \\─────────
                \\─────────
                          \\─────ooooo
	                   ──/
	                 ─/
	       	      ──/
	            ────────────
				\\──────────


<a id="org6c199b2"></a>

## ascii-art-to-unicode

I found another neat addition in the package list,
[`ascii-art-to-unicode`](https://elpa.gnu.org/packages/ascii-art-to-unicode.html), which polishes simple line drawings and
makes them look much better. Installed it. Example use:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">M-x artist-mode RET</td>
<td class="org-left">Invoke artist mode</td>
</tr>


<tr>
<td class="org-left">C-c C-a r</td>
<td class="org-left"><code>artist-select-op-rectangle</code></td>
</tr>
</tbody>
</table>

<del>---------------</del>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><del>-------</del>&#x2013;+</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

<del>-------</del>--&#x2013;&#x2014;+  |

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

<del>----------</del>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">C-c C-c</td>
<td class="org-left"><code>artist-mode-off</code></td>
</tr>


<tr>
<td class="org-left">C-x n n</td>
<td class="org-left"><code>narrow-to-region</code></td>
</tr>


<tr>
<td class="org-left">untabify region</td>
<td class="org-left"><code>untabify-region</code></td>
</tr>


<tr>
<td class="org-left">M-x aa2u RET</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

┌───────────────┐
│               │
│       ┌───────┼──┐
│       │       │  │
│       │       │  │
│       │       │  │
└───────┼───────┘  │
│          │
│          │
│          │
└──────────┘

Check the [vignette for aa2u](https://elpa.gnu.org/packages/ascii-art-to-unicode.html) for more details.


<a id="org02daa3d"></a>

# Org Tables

This approach only requires vanilla Org-mode


<a id="org67f4383"></a>

# PlantUML


<a id="orgd9ae914"></a>

# References

Rohan (Jan 17, 2015). Poor mans UML / Emacs Artist Mode [blog]. [URL:
robrohan.com](https://robrohan.com/2015/01/17/poor-mans-uml-artist-mode.html).

