all: linkcheck

# Using my original linkchecker
# https://sekika.github.io/2025/11/19/go-linkchecker/
linkcheck:
	@ linkchecker -u suzuki.html -ignore ignore.txt -wait 3 -timeout 10 -no-internal -user-agent "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36" | tee output.txt
	@ cat output.txt | grep "\[NG\]" > linkcheck.txt
	@ rm output.txt
	@ echo "===== Finished ====="
	@ cat linkcheck.txt
