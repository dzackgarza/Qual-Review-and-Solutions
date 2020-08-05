SHELL:=/bin/zsh
FILENAME="Complex_Analysis_Problems.md"

.SILENT:

compile:
	latex_preview -f $(FILENAME) -j -z
	echo "Make done"

watch:
	latex_preview -f $(FILENAME) -z

view: 
	latex_preview -f $(FILENAME) -v -z

tex:
	latex_preview -f $(FILENAME) -x -j -z

.ONESHELL:
