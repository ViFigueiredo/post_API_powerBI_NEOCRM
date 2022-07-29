# HOW TO MAKE A POST REQUEST WITH JSON BODY USING POWER QUERY (M LANGUAGE)


```
let

url = "URL",

postBody = "{
    ""method"":""POST"",
    ""token"":""YOUR_TOKEN_AUTH"",
    ""user"":""TOKEN_USER"",
    ""dataInitial"":""YYYY-MM-DD"",
    ""dataFinal"":""YYYY-MM-DD"",
    ""painelId"":""ID_PANEL""
}",

Source = Csv.Document(Web.Contents(
    url,
    [Headers = [#"Content-Type"="application/x-www-form-urlencoded"],
    Content = Text.ToBinary(postBody)]),
    [
        Delimiter=";",
        Columns=39,
        Encoding=1252
    ]
)

in Source
```
