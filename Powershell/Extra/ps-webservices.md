# Powershell en webservices

- `alias curl` - Wat kan je hieruit afleiden?
  - heeft curl echt dezelfde syntax? zie eventueel https://curl.haxx.se/docs/ of
    `man curl` op Linux
- `get-help invoke-webrequest -examples`
- `get-help invoke-restmethod -examples`
- `get-help invoke-restmethod -parameter Method`

- `invoke-restmethod api.github.com/repos/vbrh-immalle/CustomCollectionsMeasurement `
- `invoke-restmethod api.github.com/users/{username}/repos` : lijst van repositories

- Test `invoke-restmethod api.github.com/user`. Dit werkt niet o.w.v. authenticatie.

- Ga naar https://requestb.in en maak een unieke link
  - sla de link op in een variable `$reqbin`
  - kijk welke headers, welke query string en welke body wordt meegestuurd met
    volgende commando's:
    - `invoke-restmethod $reqbin`
    - `Invoke-RestMethod $reqbin -Body @{Name="joske"; Leeftijd=18}`
    - `Invoke-RestMethod $reqbin -Body @{Name="joske"; Leeftijd=18} -method Post`
    
- Gebruik https://httpbin.org om responses te krijgen, b.v.:
  - `(invoke-restmethod now.httpbin.org).now` of sla het result op in een variable `$result` en doe `$result.now`
  - `invoke-restmethod httpbin.org/post` - Welke foutmelding krijg je?
  - `invoke-restmethod httpbin.org/post -method post`
  - `invoke-restmethod httpbin.org/basic-auth/willy/wally -Credential (Get-Credential)`
  - `(invoke-restmethod httpbin.org/post -method post -ContentType application/json).headers` 
  - Experimenteer zelf m et cookies, status codes, ...
