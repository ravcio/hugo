---
title: VSCode
type: docs
math: false
weight: 4
prev: docs/folder/
---

# VSCode usage


## Find and Replace

Regex

- Find: `### P4\.(.+)`
- Replace: `### P4\.(\1)`





## Symbole wyrażeń regularnych

| kod                                               | alternatywny kod                           |
| ------------------------------------------------- | ------------------------------------------ |
| **\d**=cyfra                                      | **\D**=nie cyfra                           |
| **\w**=litera,cyfra,_                             | **\W**=nie litera,cyfra,_                  |
| **\n**=newline                                    | **.**=dowolny znak (oprócz **\n**)         |
| **\s**=space,tab,newline                          | **\S**= nie space,tab,newline              |
| **^**=początek tekstu                             | **$**=koniec tekstu                        |
| **\***=0 lub więcej (greedy)                      | **\*?**=0 lub więcej (minimalist)          |
| **+**=1 lub więcej (greedy)                       | **+?**=1 lub więcej (minimalist)           |
| **?** = 0 lub 1 (greedy)                          | **??** = 0 lub 1 (minimalist)              |
| **{m}**=dokładnie *m* razy                        | **{m,n}**=między *m* i *n* razy            |
| **\b**=granica słowa                              | **\B**=nie granica słowa                   |
| **[abc]**=jedna z liter: a,b lub c                | **[^abc]**=dowolny znak oprócz: a,b oraz c |
| **[a-z]**=dowolna litera z zakresu włącznie a i z | **[^a-z]**=dowolny znak nie z zakresu      |
| **a\|b**=albo a, albo b                           | **\\\\**=jeden znak backslash \\           |
| **(xxx)**=złap (capture) wnętrze                  | **(?:xxx)**=dopasuj (match) wnętrze        |
|                                                   |                                            |



> **Flagi:**
> - `re.DOTALL` teraz znak **.** = dowolny znak (także **\n**) ; skrót: `re.S`
> - `re.IGNORECASE` ignoruj wielkość liter ; skrót: `re.I`
> - `re.MULTILINE` znak **^**=początek linii, **$**=koniec linii ; skrót: `re.M`

```py
re.findall(pattern, string, flags=re.I|re.M|re.X)
```

Dodatkowe symbole:

- `|` - pipe (lub)
- `[^...]` - nie ze zbioru
- `\B`
- `{2}` - dokładnie dwa
- `{2, 4}` - pomiędzy dwa i cztery
- `{4,}` - cztery i więcej




