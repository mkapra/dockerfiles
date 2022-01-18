FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

# Installing LaTeX
RUN apt-get update && \
    apt-get -y install --no-install-recommends \
	texlive texlive-latex-extra texlive-extra-utils texlive-fonts-extra \
      	texlive-bibtex-extra texlive-lang-german texlive-fonts-recommended \
	tex-gyre texlive-lang-greek biber latexmk make git procps locales curl
RUN rm -rf /var/lib/apt/lists/*

# Generating locales
RUN sed -i -e 's/# de_DE.UTF-8 UTF-8/de_DE.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=de_DE.UTF-8
ENV LANGUAGE=de_DE.UTF-8 LANG=de_DE.UTF-8 LC_ALL=de_DE.UTF-8

WORKDIR /workdir
