# Advanced Console Tricks

## Foreach-Object Advanced Syntax

```ps
(Get-Process).Id
```

can expressed by a pipeline command

```ps
Get-Process |% Id
```

which translates to 

```ps
Get-Process | Foreach-Object { $_.Id }
```

This short form of writing `Foreach-Object` is actually also available for method calls:


```ps
Get-Process |% WaitForExit 55
```


### Advantages
you dont have to go to the beginning of the line, and put an opening brace there.  
An alternative solution to this is `Select-Object -ExpandProperty`, but its much longer.
