# Introduction
These LaTeX files provide a template for the UNCW Reappointment, Tenure, and Promotion Form. Examples are provided.
- `main.tex` - the primary document
- `courses.tex` - aggregator of supporting course materials in the `courses/` subdirectory
- `obs.tex` - aggregator for peer observations in the `obs/` subdirectory
- `pubs.tex` - aggregator for publications in the `pubs/` subdirectory

This template is current with the UNCW RTP form approved by UNCW Faculty Senate and last revised 5/19. 

[UNCW Reappointment, Tenure, and Promotion information page](https://uncw.edu/aa/rpt/rtp%20information%20page.html)

# Publication references
Change the command `\addbibresource{my-collection.bib}` to reference your BibTex file. 

1. References to publications __with__ PDFs to be included in the document should follow instructions under "Linking and including files"
1. References to publications __without__ PDFs (e.g., websites, presentations, software) that should be rendered only as a formatted citation should use the `\fullcite` BibLaTeX command.


# Linking and including files
The template can include the full-text of publications, peer observations, and course sample materials based on filename. Filenames must not include LaTeX command characters and must have the `.pdf` extension. 

## Publications
`pubs.tex` should contain publications and PDFs are in the `/pubs` subdirectory.

In `pubs.tex`, this command injects the full PDF of the file `pubs/Layman2020.pdf` and creates a hyperlink target `Layman2020`:
```
    \sm{Layman2020}
```

In `main.tex`, this command creates a citation followed by a hyperlink to the target `Layman2020`:
```
    \smref{Layman2020}
```


## Peer Observations and Course Materials
- `courses.tex` contains course materials and PDFs are in the `/courses` subdirectory.
- `obs.tex` should contain peer observations materials and PDFs are in the `/obs` subdirectory.

In `courses.tex`, this commands injects the full PDF of the file `courses/242 FA18 Syllabus.pdf` contains the content to include. `CSC 242 Syllabus` is the hyperlink target:
```
    \sm{CSC 242 Syllabus}{242 FA18 Syllabus.pdf}
```

In `main.tex`, this command creates a link text "Syllabus" that will jump to the included PDF later in the document.
```
    \hyperref[CSC 242 Syllabus]{Syllabus}
```

## Rendering included PDFs with the `\sm` command
The `\sm` command is defined at the top of `courses.tex`, `pubs.tex`, and `obs.tex` and handles both the creation of hyperlink targets and the rendering of the included PDFs. You may need to tweak this command to get the injected PDFs scaled properly.