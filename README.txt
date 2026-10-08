UCY–Daedalus Research Poster Template

Template specifications
  A0 landscape (1189 × 841 mm), three columns, compiled with LuaLaTeX.
  Pale gold header with a centred title and a single author/affiliation line.
  Section headings use dark blue bars (#245781) with bold white text aligned left.
  Both horizontal separator rules are gold (#E5AA16) and 0.10 cm thick.
  The header places UCY on the left and Daedalus on the right.
  The footer places references on the left and the funding area on the right.
  DNCSgroup, MINERVA and ERC sit above the funding text, without a heading.
  The body text, author names, figure panels and references are placeholders.

Files
  poster.tex               Main document and poster content; compile this file.
  poster-config.tex        Title, authors, affiliation, references and logo settings.
  ucy-style.tex            Shared colours, fonts, layout, header and footer.
  beamerthemegemini.sty    Original Gemini theme; usually requires no changes.
  graphics/               Logo assets; add research figures here as needed.
  .latexmkrc              Sets LuaLaTeX as the default compiler for local latexmk.
  .gitignore              Excludes auxiliary files and the build/ directory.
  GEMINI-LICENSE.md       Original MIT license for the Gemini theme.
  poster.pdf              Preview of the current template.

Getting started
  1. Copy the entire template directory to start a new poster project.
  2. Edit the title, authors, affiliation and references in poster-config.tex.
     Keep \and between authors; the header displays names separated by commas.
  3. Replace the body text, sample equation and three figure panels in poster.tex.
  4. For posters outside MINERVA, change \projectlogostrue to \projectlogosfalse.
     This hides the project/funder logos and acknowledgement while retaining
     the UCY/Daedalus header logos. DNCSgroup is in the hidden footer area.
  5. To change the poster size, edit the beamerposter options in poster.tex.
     After changing dimensions or title length, check line wrapping, figure sizes
     and content overflow.

Replacing figure panels
  Replace \figureplaceholder{Description}{Height} with:
    \includegraphics[width=\linewidth]{graphics/your-figure.pdf}
  Update the caption below it. PDF, PNG and JPG are supported; preserve aspect ratios.
  To display results across two columns, merge the middle and right columns and
  adjust their widths and spacing.

Optional QR code
  To add a QR code immediately to the left of the title text, define:
    \newcommand{\posterqrcode}{graphics/QRcode.pdf}
  Use a transparent vector PDF with an empty margin for clear printing.
  The header background shows through the QR code; no caption is displayed.
  The QR code is 5.4 cm square; the title remains centred between equal side areas.
  The QR code is positioned
  beside the title without changing the title or affiliation alignment.
  Define \posterqrurl with the encoded URL to make the code clickable in the PDF.
  Supply your own QR asset at the configured path; no QR asset is bundled.
  If using SVG, convert it to PDF before compiling; only the PDF is required.

Local compilation
  Verified with TeX Live 2024, using the Lato and Raleway fonts required by Gemini.
  With a complete TeX Live installation, run from the template root directory:
    latexmk -outdir=build poster.tex
  The output is build/poster.pdf. Auxiliary files stay in build/ to keep the root tidy.
  .latexmkrc selects LuaLaTeX; latexmk reruns the compiler as needed.
  If your editor explicitly selects pdflatex, change its compiler to LuaLaTeX.
  Without latexmk, run this command twice:
    lualatex -interaction=nonstopmode -halt-on-error poster.tex
  This places the PDF and auxiliary files in the root directory.
  If a PDF viewer locks the output file, close that PDF and compile again.

Overleaf
  Create a blank project and upload these files, preserving the graphics/ directory:
    poster.tex, poster-config.tex, ucy-style.tex, beamerthemegemini.sty,
    the logo PNGs and vector PDFs in graphics/, and GEMINI-LICENSE.md.
  Select poster.tex as the main document and LuaLaTeX as the compiler, then compile.
  Local build files, old PDFs, auxiliary files and preview images do not need uploading.

Theme source
  Gemini by Anish Athalye and contributors
  https://github.com/anishathalye/gemini
  https://www.overleaf.com/latex/templates/gemini-poster-theme/nzpspqjryjhx
  Gemini's original MIT license is preserved in GEMINI-LICENSE.md.
  Supplied SVG logos are retained unchanged. LaTeX uses cropped vector PDFs:
    graphics/Daedalus_Research_Centre_flat-wing.pdf
    graphics/DNCSgroup.pdf
  DNCSgroup uses the supplied artwork with left-aligned text.
  If either SVG changes, regenerate its PDF with Inkscape, for example:
    inkscape graphics/DNCSgroup.svg --export-area-drawing --export-type=pdf --export-filename=graphics/DNCSgroup.pdf
  Edit \posterfundingfirstline and \posterfundingsecondline in ucy-style.tex
  to change the funding text. Its block is sized to the longer line and
  positioned at the right edge, with both funding lines justified.
  The flat-wing Daedalus variant lowers the wing tip while preserving the
  lettering and main emblem. The original vector SVG/PDF remain available.
