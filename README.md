# elm-pep

[![][badge-license]][license]

[badge-license]: https://img.shields.io/badge/license-MPL--2.0-blue.svg?style=flat-square
[license]: https://www.mozilla.org/en-US/MPL/2.0/

Minimalist [pointer events][pointer-events] polyfill.

Contrary to the current standard polyfill for pointer
events ([jquery/PEP][jquery-pep]), this polyfill provides
the `offsetX` and `offsetY` properties and
is compatible with elm JSON decoders (no cyclic attributes).

## Usage

Import elm-pep.js in your web page and
add an `elm-pep` attribute to the DOM element
on which you have attached pointer events listeners.

The implemented pointer events are:

* pointerdown
* pointermove
* pointerup

If the `PointerEvent` API is not supported in the browser,
this will attach mouse and touch events to the document.
When triggered, we check if the target has the `elm-pep`
attribute and in that case, transform the mouse or touch
event into a pointer event and dispatch it.

## Caveats

**This is not a fully featured polyfill.**

This code is truly minimalist and simple so
probably not very computing efficient.
It does not aim at supporting old browsers,
only [recent browsers that do not support
pointer events yet][caniuse-pointer].

This code focuses on unifying the touch and mouse APIs and
thus only provides the `pointerId` and `isPrimary`
properties specific to pointer events.

[pointer-events]: https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent
[caniuse-pointer]: https://caniuse.com/#feat=pointer
[jquery-pep]: https://github.com/jquery/PEP

## Authors

Matthieu Pizenberg: matthieu@pizenberg.com
Thomas Forgione: thomas@tforgione.fr
