# GoLang

## App.go

Steps/stages to complete:

1. Open an IDE (VisualCode)
2. Open a new folder, I created ```GOLANG```
3. Open a terminal in VSC
4. Run the following ```go mod init github.com/butlerpaul1987/GoLang```
5. Run the file to pull colly files ```go get -u github.com/gocolly/colly/...```
6. Add the following steps:

Add the main package
```package main```

Add the colly collector
```
func main() {
    c := colly.NewCollector(
        colly.AllowedDomains("en.wikipedia.org"),
    )
}
```

Import the files needed
```
import (
    "fmt"
    "github.com/gocolly/colly"
)
```

Example script:
```
// Find and print all links
    c.OnHTML(".mw-parser-output", func(e *colly.HTMLElement) {
        links := e.ChildAttrs("a", "href")
        fmt.Println(links)
    })
    c.Visit("https://en.wikipedia.org/wiki/Web_scraping")
```
