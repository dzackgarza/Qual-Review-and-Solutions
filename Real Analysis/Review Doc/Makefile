SHELL:=/bin/zsh
FILENAME="Real_Analysis_Qual_Notes.md"

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
