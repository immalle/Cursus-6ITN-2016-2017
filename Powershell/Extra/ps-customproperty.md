
```
dir .. | select -Property length, name, lastwritetime, @{name="my column (property)"; expression={ $_.LastWriteTime.DayOfWeek }}
```
