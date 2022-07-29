# 

let

url = "URL",

postBody = "{
    ""method"":""POST"",
    ""tokenEstrutura"":""YOUR_TOKEN_AUTH"",
    ""tokenUsuario"":""TOKEN_USER"",
    ""dataInicial"":""YYYY-MM-DD"",
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
