all:

linkcheck-html:
	linkchecker -C --output=html suzuki.html | tee linkcheck.html

linkcheck:
	linkchecker -C --output=blacklist suzuki.html | grep -v 88_files | awk '{print $$2}' | sort > linkcheck
	diff alive.txt linkcheck | grep ">" | awk '{print $$2}' > 404.txt
