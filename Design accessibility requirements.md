criteria WCAG for android apps
TLDR; 
- visual components reused throughout the app should be consistent/look the same
- Buttons etc should be labelled clearly
- Design should be explicit - user should rely on clear labelling and headers and not only colours and shapes
- a clear sequence of going through the app should be established (i.e. navigational buttons look the same, placed the same across pages)
- the purpose of any links should be apparent
- Status messages should be clear and direct
- text spacing ratios?

**WCAG:** Success Criterion 1.1.1 Non-text Content - non-text should have [alt-text] attached

**WCAG:** Success Criterion 1.3.1 Info and Relationships - presentation should be intuitive or labelled
"Information, [structure](https://www.w3.org/TR/WCAG22/#dfn-structure "The way the parts of a web page are organized in relation to each other; and The way a collection of web pages is organized"), and [relationships](https://www.w3.org/TR/WCAG22/#dfn-relationships "meaningful associations between distinct pieces of content") conveyed through [presentation](https://www.w3.org/TR/WCAG22/#dfn-presentation "rendering of the content in a form to be perceived by users") can be [programmatically determined](https://www.w3.org/TR/WCAG22/#dfn-programmatically-determinable "determined by software from author-supplied data provided in a way that different user agents, including assistive technologies, can extract and present this information to users in different modalities") or are available in text."

also look at accessibility provided by platform software Android API again have a look

**WCAG:** Success Criterion 1.3.2 Meaningful Sequence - sequence of content presented affects its meaning. correct reading sequence is programmatically determined

**WCAG:** Success Criterion 1.3.3 Sensory Characteristics - components are direct and understanding isn't relied on by shape, colour etc. 

**WCAG:** Success Criterion 1.4.1 Use of Color- colour is not the only relied upon feature to determine functionality

**WCAG:** Success Criterion 1.3.4 Orientation 
orientation doesn't affect the readability or usability of app

**WCAG:** Success Criterion 1.4.3 Contrast (Minimum)
The visual presentation of [text](https://www.w3.org/TR/WCAG22/#dfn-text "sequence of characters that can be programmatically determined, where the sequence is expressing something in human language") and [images of text](https://www.w3.org/TR/WCAG22/#dfn-images-of-text "text that has been rendered in a non-text form (e.g., an image) in order to achieve a particular visual effect") has a [contrast ratio](https://www.w3.org/TR/WCAG22/#dfn-contrast-ratio "(L1 + 0.05) / (L2 + 0.05), where") of at least 4.5:1, except for the following:

Large Text
[Large-scale](https://www.w3.org/TR/WCAG22/#dfn-large-scale "with at least 18 point or 14 point bold or font size that would yield equivalent size for Chinese, Japanese and Korean (CJK) fonts") text and images of large-scale text have a contrast ratio of at least 3:1;


**WCAG2ICT:** Applying SC 1.4.4 Resize Text to Non-Web Documents and Software - allow the user in-app to zoom in text up without use of an accessibility software

**WCAG:** Success Criterion 1.4.12 Text Spacing 
- Line height (line spacing) to at least 1.5 times the font size;
- Spacing following paragraphs to at least 2 times the font size;
- Letter spacing (tracking) to at least 0.12 times the font size;
- Word spacing to at least 0.16 times the font size.

**WCAG:** Success Criterion 2.4.2 Page Titled

**WCAG:** Success Criterion 2.4.3 Focus Order - page navigation should have clearly marked buttons, repeating in design for continuity

**WCAG:** Success Criterion 2.4.4 Link Purpose (In Context) - link purpose is apparent

**WCAG:** Success Criterion 2.4.6 Headings and Labels - describe logic and purpose

**WCAG:** Success Criterion 2.4.11 Focus Not Obscured (Minimum) - keyboard doesn't obscure screen

**WCAG:** Success Criterion 3.1.1 Language of Page - should be readable, determinable, recognisable as a human language

**WCAG:** Success Criterion 3.2.1 On Focus - clicking on stuff does not change the rest of the page

**WCAG:** Success Criterion 3.2.4 Consistent Identification - components of the same functionality are identified consistently

**WCAG:** Success Criterion 4.1.3 Status Messages - status messages should be determinable 

https://www.w3.org/TR/wcag2mobile-22/


