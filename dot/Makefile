all: slides.pdf README.md
slides.pdf: slides.Rmd
	Rscript -e "rmarkdown::render('$<', output_format = 'beamer_presentation', output_file = '$@')"
README.md: slides.Rmd
	Rscript -e "rmarkdown::render('$<', output_format = 'github_document', output_file = '$@')"
