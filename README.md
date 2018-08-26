## jsCodonWheel

This widget is an interactive version of the widely-used circular chart that translates DNA codons into the resulting amino acids. It displays the path from the center of the wheel (reflecting the first nucleotide of the codon) to the periphery (the third nucleotide) and the resulting amino acid(s). Two paths can be shown at once, to compare the effects of a point mutation/single nucleotide variant. Detailed information about each amino acid is presented below the text input fields, allowing side-by-side comparison of wild-type and variant amino acids.

### Using the widget
The codon wheel can be used in two main modes: text input and click/touch. Using the text inputs, enter three letters representing the codon itself (A, T, C, G), the single- or three-letter code for an amino acid, or the full name of the amino acid. The widget is not case sensitive, so either upper or lower case input is acceptable. You can also select an amino acid by clicking or touching the outer rings of the wheel. 

[Try it out on the demo page!](https://pearcetm.github.io/jscodonwheel)

### Embedding the widget
jsCodonWheel can be embedded in a webpage by including the jscodonwheel.js JavaScript file. In addition, svg elements representing the amino acid structures should be included in the html of the page. The individual structures are referenced using an `href:xlink` to the id attribute, which is expected to be in the form `#aa-X` where `X` is the lower-case character of the single-letter amino acid code.

Including the script exposes a function `Codonwheel()` which creates the JavaScript widget. The widget's API consists of a single function, `init(options)`. This function configures the widget and draws the graphical elements into the HTML document.

### Configuration options:

#### target: selector string
The target option defines where to create the widget. If a target is not provided, a `<div>` with class `codonwheel` is created and appended to the body of the document, and used to contain the widget.

#### colors: object
The colors option allows overriding the default colors of the background widget, wildtype and variant amino acids.

#### biophysical_data: object
The keys of this object are the one-letter amino acid codes, and the corresponding values are arrays which define the biophysical properties to be displayed. For example:

    {
        H: [{'Side chain':'Imidazole'}, {'Charge':'Positive'}, {'Hydropathy':'Moderate'}],
        ...
    }

#### Default options
Default options are defined below.
```
default_options={
    target: '',
    colors: {
        background:'white',
        wildtype: 'rgb(210,255,200)',
        mutant: 'rgb(255,200,210)',
    },
    biophysical_data:{...},//see source code
}
```
