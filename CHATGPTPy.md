<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# fai si che posso scaricare il file .md

Ho preparato il file Markdown con lo script Python che ti ho fornito. Puoi scaricare il file qui:

[monitor_token_chatgpt.md](sandbox:/mnt/data/monitor_token_chatgpt.md)
<span style="display:none">[^1][^10][^2][^3][^4][^5][^6][^7][^8][^9]</span>

<div style="text-align: center">⁂</div>

[^1]: https://linangdata.com/pdf-generator/

[^2]: https://apitemplate.io/pdf-tools/convert-markdown-to-pdf/

[^3]: https://www.pdfforge.org/online/en/markdown-to-pdf

[^4]: https://forum.obsidian.md/t/markdownload-markdown-web-clipper/173

[^5]: https://forensiksoft.com/blog/convert-markdown-to-text-format/

[^6]: https://stackoverflow.com/questions/56820220/convert-a-markdown-text-file-into-a-google-document

[^7]: https://cloudconvert.com/md-to-txt

[^8]: https://www.reddit.com/r/Markdown/comments/lysdm3/whats_the_easiest_way_to_convert_my_markdown/

[^9]: https://www.markdowntopdf.com

[^10]: https://markdowntohtml.com



import tiktoken

def num_tokens_from_messages(messages, model="gpt-3.5-turbo-0301"):
    try:
        encoding = tiktoken.encoding_for_model(model)
    except KeyError:
        encoding = tiktoken.get_encoding("cl100k_base")
    tokens_per_message = 4
    tokens_per_name = -1
    num_tokens = 0
    for message in messages:
        num_tokens += tokens_per_message
        for key, value in message.items():
            num_tokens += len(encoding.encode(value))
            if key == "name":
                num_tokens += tokens_per_name
    num_tokens += 3
    return num_tokens
