# RLIG (Required Ligatures) Test for Adobe Illustrator

## The problem

Adobe Illustrator [does not properly support](https://illustrator.uservoice.com/forums/333657-illustrator-desktop-feature-requests/suggestions/33434134-opentype-ligature-features-ccmp-and-rlig-do-not-wo) the [`rlig`](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt#tag-rlig) OpenType feature. This is lagging behind many applications, including web browsers, InDesign, web browsers, Font Goggles, Figma, Sketch, Keynote, Windows 11 Word (once ligatures are activated in settings), and more.

The only workaround is to turn on one of the “Middle Eastern” line composers (as of Illustrator 2023, Version 27). This is a rough and completely unguessable process for normal, everyday users:

1. Navigate to Illustrator > Preferences > Type
2. Click the checkbox “Show Indic Options”
3. Then, open the Paragraph panel (Window > Type > Paragraph)
4. Open the hamburger/flyout menu of the Paragraph panel, and select “Middle Eastern & South Asian Every-line Composer”

This is problematic because `rlig` is used not only for Arabic type, but also commonly recommended for alternate glyphs in cases like substitutions along certain variable axes (e.g. a dollar sign losing the middle part of its vertical bar when the font weight gets too bold). It is also commonly recommended for glyph alternates in script/handwriting fonts, where the alternate glyphs are not intended to be optional.

## How should it work?

It should ”just work,” as it does in most other apps. Users should not have to go into multiple settings panels to enable a basic feature which is required for the proper display of many script typefaces and variable fonts.

## Test font

This repo contains a very simple test font. It contains one character, `A`, which has a high crossbar by default, which swaps to a low crossbar at `wght` values at `550` and above. This substitution uses the `rlig` feature – so unfortunately, it doesn’t work in the typical Adobe Illustrator setup.

This test font is given an OFL license, in case it might be helpful to Adobe for testing and addressing this issue.
