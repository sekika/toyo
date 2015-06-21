all:

linkcheck:
	linkchecker -C --output=html suzuki.html | tee linkcheck.html

remote:
	linkchecker -C --output=blacklist http://www2.toyo.ac.jp/~seki_k/kankyo/suzuki.html | grep -v 88_files | awk '{print $$2}' | sort > linkcheck
	diff alive.txt linkcheck | grep ">" | awk '{print $$2}' > 404.txt
