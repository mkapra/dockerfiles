# LaTeX Container
Container for building LaTeX documents

## Usage
### Docker
Build the container first:
```bash
docker build -t linux .
```

Then you can run this command to execute latexmk and get the resulting PDF
```bash
docker run --rm -it -v $(pwd):/workdir latex latexmk -pdf document.tex
```

### VS Code
Requirements:

* Extension: ![LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
* Docker Image: The docker image from above

If all requirements are fullfilled these settings have to be set in VS Code:
```
"latex-workshop.view.pdf.viewer": "tab",
"latex-workshop.docker.enabled": true,
"latex-workshop.docker.image.latex": "latex"
```
