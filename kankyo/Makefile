all:

linkcheck-html:
	linkchecker -C --output=html suzuki.html | tee linkcheck.html

linkcheck:
	linkchecker -C --output=blacklist suzuki.html | grep -v 88_files | awk '{print $$2}' | sort > linkcheck
	diff alive.txt linkcheck | grep ">" | awk '{print $$2}' > 404.txt

list:
	@ grep href suzuki.html | sed -e 's/^.*href=\"//' | sed -e 's/\".*$$//' | sort | grep -v "^#" | grep -v "^\.\.\/"

host:
	@ make list | sed -e 's/http:\/\///' | sed -e 's/https:\/\///' | sed -e "s/\/.*$$//" | sort | uniq -c | sort -n

count:
	@ make list | wc -l
