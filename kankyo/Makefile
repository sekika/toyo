all:

# python3 -m pip install linkchecker

linkcheck-html:
	linkchecker --check-extern --output=html suzuki.html | tee linkcheck.html

linkcheck: suzuki.html Makefile
	linkchecker --check-extern -o blacklist suzuki.html | grep -v 88_files | awk '{print $$3}' | grep -v "doi.org" | grep -v "jstor.org" | sed -e 's/^.//' | sed -e 's/...$$//' | sort > linkcheck

list:
	@ grep href suzuki.html | sed -e 's/^.*href=\"//' | sed -e 's/\".*$$//' | sort | grep -v "^#" | grep -v "^\.\.\/"

host:
	@ make list | sed -e 's/http:\/\///' | sed -e 's/https:\/\///' | sed -e "s/\/.*$$//" | sort | uniq -c | sort -n

count:
	@ make list | wc -l
