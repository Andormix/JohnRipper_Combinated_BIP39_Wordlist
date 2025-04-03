+ For Windows PowerShell, use: 

Get-Content C:\path\to\bip39.txt | ForEach-Object { $word1 = $_; Get-Content C:\path\to\bip39.txt | ForEach-Object { "$word1$_" } } | Set-Content C:\path\to\combined_bip39.txt

+ Bash Script (Linux/Mac):

while read word1; do
    while read word2; do
        echo "${word1}${word2}"
    done < bip39.txt
done < bip39.txt > combined_bip39.txt

+ Python: 

bip39_file = "C:\\path\\to\\bip39.txt"
output_file = "C:\\path\\to\\combined_bip39.txt"

with open(bip39_file, "r", encoding="utf-8") as f:
    words = [line.strip() for line in f]

with open(output_file, "w", encoding="utf-8") as f:
    for word1 in words:
        for word2 in words:
            f.write(f"{word1}{word2}\n")

print(f"Combined wordlist saved to {output_file}")
