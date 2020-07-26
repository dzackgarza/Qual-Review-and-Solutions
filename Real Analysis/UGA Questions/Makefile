SHELL:=/bin/zsh
FILENAME="UGA_Real_Analysis_Qual_Questions.md"

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
