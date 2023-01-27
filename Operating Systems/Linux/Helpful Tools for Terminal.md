### Lq is a tool to parse json
Download using (if on mac):
> brew install lq

Use | lq to parse JSON:

Example:
> kubectl get cluster test-odd-wire -o json | jq .metadata

### **MAC ONLY: [pbcopy and pbpaste](https://medium.com/@codenameyau/how-to-copy-and-paste-in-terminal-c88098b5840d):**
# This will copy all the content within a file.
> cat myfile.txt | pbcopy

# This will output the contents of your clipboard.
> pbpaste