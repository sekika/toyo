all:

# pip install linkchecker

linkcheck-html:
	linkchecker -C --check-extern --output=html suzuki.html | tee linkcheck.html

linkcheck: suzuki.html Makefile
	linkchecker -C --check-extern --output=blacklist suzuki.html | grep -v 88_files | awk '{print $$3}' | sort > linkcheck
	diff alive.txt linkcheck | grep ">" | awk '{print $$2}' | sed -e 's/u//' | sed -e 's/^.//' | sed -e 's/...$$//' > 404.txt

list:
	@ grep href suzuki.html | sed -e 's/^.*href=\"//' | sed -e 's/\".*$$//' | sort | grep -v "^#" | grep -v "^\.\.\/"

host:
	@ make list | sed -e 's/http:\/\///' | sed -e 's/https:\/\///' | sed -e "s/\/.*$$//" | sort | uniq -c | sort -n

count:
	@ make list | wc -l
