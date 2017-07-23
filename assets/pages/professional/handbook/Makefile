ODT_FILES=$(wildcard student.odt parent.odt teacher.odt)

%.pdf: %.odt
	soffice --convert-to pdf "$<"

all: $(ODT_FILES:.odt=.pdf)

.PHONY: all
