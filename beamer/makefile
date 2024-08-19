

quickps:
	rm -f modefile.tex
	latex main.tex ; dvips main 

quickpdf:
	make quickps ; ps2pdf main.ps

slides:
	rm -f modefile.tex
	latex main.tex ; latex main.tex ; dvips main ; ps2pdf main.ps
	mv -f main.pdf lecXX.pdf
	rm -f main.ps
#	read -p "Rename lecXX.pdf to lec__.pdf... (any key continues)"
	echo "Rename lecXX.pdf to lec__.pdf... "
	printf "\n mv -f lecXX.pdf lec__.pdf    \n\n"
	printf "\n\n comment logo in/out as needed    \n\n"

handouts:
#	echo '\changemode{handout}'
#	echo '\changemode{handout}' | cat >> modefile.tex
	printf '\changemode{handout}\n' > modefile.tex
#	echo "\\changemode{handout}" > modefile.tex
	cat modefile.tex
#	read -p "Is modefile.tex OK?... (any key continues)"
	latex main.tex ; latex main.tex ; dvips main ; ps2pdf main.ps
	pdfnup --nup 2x4 --frame true --no-landscape --scale 0.95 main.pdf
	mv -f main-nup.pdf print8lecXX.pdf
	echo "mv -f print8main.pdf print8lecXX.pdf"
	pdfnup --nup 2x4 --frame true --no-landscape --scale 0.95 main.pdf
	mv -f main-nup.pdf print8lecXX.pdf
	pdfnup --nup 2x2 --frame true --scale 0.95 main.pdf
	mv -f main-nup.pdf print4lecXX.pdf
	pdfnup --nup 1x2 --frame true --no-landscape --scale 0.95 main.pdf
	mv -f main-nup.pdf print2lecXX.pdf
	mv -f main.pdf print1lecXX.pdf
	rm -f modefile.tex main.pdf main.ps
#	read -p "Rename print_main.pdf to print_lecXX.pdf... (any key continues)"
	echo "Rename print_main.pdf to print_lecXX.pdf... "
	printf "\n mv -f print8lecXX.pdf print8lec__.pdf \n mv -f print4lecXX.pdf print4lec__.pdf    \n\n"
	printf "\n\n comment logo in/out as needed    \n\n"

all:
#	read -p "Has logo command been restored?  ...  (any key continues)"
	make slides
	make handouts
#	read -p "Rename ...main.pdf to ...lecXX.pdf... (any key continues)"
	echo "H E L P E R S ..... Rename ...main.pdf to ...lecXX.pdf... "
	printf "\n mv -f lecXX.pdf lec__.pdf \n\n"
	printf "\n mv -f print8lecXX.pdf print8lec__.pdf \n mv -f print4lecXX.pdf print4lec__.pdf    \n\n"
	printf " latex main && latex main && latex main && make all"
	printf " mv -f lecXX.pdf lec0x.pdf;  mv -f print4lecXX.pdf print4lec0x.pdf; mv -f print8lecXX.pdf print8lec0x.pdf"
	printf " mv *lec0x.pdf ../../lec"
	printf "\n\n comment logo in/out as needed    \n\n"
	
	
test:
	printf "\n mv -f print8lecXX.pdf print8lec__.pdf \n mv -f print4lecXX.pdf print4lec__.pdf    \n\n"
	
latex:
	make all
	echo "Rename ...main.pdf to ...latexXX.pdf... "
	printf "\n mv -f lecXX.pdf latex__.pdf \n\n"
	printf "\n mv -f print8lecXX.pdf print8latex__.pdf \n mv -f print4lecXX.pdf print4latex__.pdf    \n\n"
	
# read -p "First: edit handout mode in for both files... (any key continues)"
# vi +1 impint1.tex
# vi +2 impint2.tex
# 
# latex impint1.tex ; latex impint1.tex 
# latex impint2.tex ; latex impint2.tex 
# 
# dvips impint1 ; ps2pdf impint1.ps
# pdfnup --nup 2x4 --frame true --no-landscape --scale 0.95 impint1.pdf
# mv -f impint1-nup.pdf impint1print8.pdf
# dvips impint2 ; ps2pdf impint2.ps
# pdfnup --nup 2x4 --frame true --no-landscape --scale 0.95 impint2.pdf
# mv -f impint2-nup.pdf impint2print8.pdf
# 
# read -p "Second: edit handout mode out for both files... (any key continues)"
# vi +1 impint1.tex
# vi +2 impint2.tex
# 
# latex impint1.tex ; latex impint1.tex 
# latex impint2.tex ; latex impint2.tex 
# 
# dvips impint1 ; ps2pdf impint1.ps
# dvips impint2 ; ps2pdf impint2.ps

collected:
	cd ../../lec; ls print8lec*.pdf ; \
	pdftk print8lec01.pdf print8lec02.pdf print8lec03.pdf print8lec04.pdf \
	      print8lec05.pdf print8lec06.pdf print8lec07.pdf print8lec08.pdf \
	      print8lec09.pdf print8lec10.pdf print8lec11.pdf print8lec12.pdf \
	      print8lec13.pdf print8lec14.pdf print8lec15.pdf print8lec16.pdf \
	      print8lec17.pdf print8lec18.pdf print8lec19.pdf print8lec20.pdf \
	      print8lec21.pdf print8lec22.pdf \
	      print8latex01.pdf print8latex02.pdf print8latex03.pdf print8latex04.pdf \
	 cat output print8collected.pdf
#	      print8lec21.pdf print8lec22.pdf print8lec23.pdf print8lec24.pdf \

	cd ../../lec; ls print4lec*.pdf ; \
	pdftk print4lec01.pdf print4lec02.pdf print4lec03.pdf print4lec04.pdf \
	      print4lec05.pdf print4lec06.pdf print4lec07.pdf print4lec08.pdf \
	      print4lec09.pdf print4lec10.pdf print4lec11.pdf print4lec12.pdf \
	      print4lec13.pdf print4lec14.pdf print4lec15.pdf print4lec16.pdf \
	      print4lec17.pdf print4lec18.pdf print4lec19.pdf print4lec20.pdf \
	      print4lec21.pdf print4lec22.pdf \
	      print4latex01.pdf print4latex02.pdf print4latex03.pdf print4latex04.pdf \
	 cat output print4collected.pdf
#	      print4lec21.pdf print4lec22.pdf print4lec23.pdf print4lec24.pdf \

	cd ../../lec; ls lec*.pdf ; \
	pdftk lec01.pdf lec02.pdf lec03.pdf lec04.pdf \
	      lec05.pdf lec06.pdf lec07.pdf lec08.pdf \
	      lec09.pdf lec10.pdf lec11.pdf lec12.pdf \
	      lec13.pdf lec14.pdf lec15.pdf lec16.pdf \
	      lec17.pdf lec18.pdf lec19.pdf lec20.pdf \
	      lec21.pdf lec22.pdf \
	      latex01.pdf latex02.pdf latex03.pdf latex04.pdf \
	 cat output leccollected.pdf
#	      lec21.pdf lec22.pdf lec23.pdf lec24.pdf \

clean:
	rm -f *.vrb *.aux *.log *.nav *.dvi *.out *.ps *.ps[1-9] *.p[1-9][0-9] 
	rm -f *.snm *.toc modefile.tex

spotless:
	make clean && rm -f lecXX.pdf print?lecXX.pdf
