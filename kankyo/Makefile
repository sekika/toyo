all:

linkcheck:
	linkchecker -C --output=html suzuki.html | tee linkcheck.html

remote:
	linkchecker -C --no-warnings http://www2.toyo.ac.jp/~seki_k/kankyo/suzuki.html | tee linkcheck.txt
