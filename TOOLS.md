---
layout: default
title: "Tools"
permalink: '/tools'
---
<script src="{{ base.url | prepend: site.url }}/assets/libs/jsonlint.js"></script>

<textarea id="jsonText" name="jsonText"
          rows="4" cols="2" placeholder="Cole seu json aqui">
</textarea>

<script>
// self executing function here
    (()=> {
        $('#jsonText').on('change', ()=> {
            console.log("trocou o valor")
        });
        console.log("Carregou o js")
    })();
</script>

