# Browser

## DOM (Document object model)

DOM represents HTML OR XML document in tree like structure where.

Browser has DOM parser which takes raw HTML, and turns it into a structured tree. Using JS we can access and modify/manipulate this tree making make page intractive and dynamic. This manipulation are costly in term of computing power & coding effort so React has Virtual-DOM(copy of DOM), instead of changing entire DOM react performs operations on copy of DOM so only updated elements get update not the entire DOM.
