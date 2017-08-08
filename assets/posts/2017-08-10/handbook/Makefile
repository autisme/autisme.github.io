ODT_FILES=$(wildcard student.odt parent.odt teacher.odt)

%.pdf: %.odt
	soffice --convert-to pdf "$<"

%.png: %.pdf
	convert "$<"[0] -thumbnail 800x800 -bordercolor white -background black +polaroid "$@"

all: $(ODT_FILES:.odt=.pdf) $(ODT_FILES:.odt=.png)

.PHONY: all
