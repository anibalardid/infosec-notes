# Oneliners

- oneliner to get links from the target itself
```bash
for h in $(cat hosts.txt); do curl -siL https://$h|sed -n -E "s/.*<.*(href|src|url)[=:]['\"]?([^'\">]+).*/\2/p" ; done	
```

- la salida del assetfinder (busca subdominios) se la pasa al httprobe (busca servicios HTTP prendidos) y lo saca a salida.txt
```bash
assetfinder --subs-only dominio.com | httprobe | tee -a subs.txt
```

Escaneo de dominios y subdominios

```bash
cat all-domain-extensions.txt | sed 's/FUZZ/redbull/gi' | assetfinder --subs-only | httpx 
```

Oneliner para buscar patrones en todos los objetos de un repositorio GIT (by @tomnomnom)  
```bash
{ find .git/objects/pack/ -name "*.idx"|while read i;do git show-index < "$i"|awk '{print $2}';done;find .git/objects/ -type f|grep -v '/pack/'|awk -F'/' '{print $(NF-1)$NF}'; }|while read o;do git cat-file -p $o;done|grep -E '<pattern>'  
```

https://github.com/KingOfBugbounty/KingOfBugBountyTips  

https://github.com/twseptian/oneliner-bugbounty  

https://github.com/dwisiswant0/awesome-oneliner-bugbounty  

