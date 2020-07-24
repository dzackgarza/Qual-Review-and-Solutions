SHELL:=/bin/zsh
FILENAME="Algebra_Qual_Notes.md"
TITLE="Algebra Qualifying Exam Notes"


renew: 
	cat sections/*.md > $(FILENAME)
	echo "Done"

compile:
	make renew
	latex_preview -f $(FILENAME) -j
	echo "Make done"

watch:
	make renew
	latex_preview -f $(FILENAME) 

view: 
	make renew
	latex_preview -f $(FILENAME) -v

.ONESHELL:

