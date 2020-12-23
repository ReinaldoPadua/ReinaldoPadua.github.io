---
layout: default
title: "Tools"
permalink: '/tools'
---
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<link href="{{ base.url | prepend: site.url }}/assets/css/jsonviewer.css" rel="stylesheet" />
<script src="{{ base.url | prepend: site.url }}/assets/libs/jsonviewer.js"></script>


<textarea id="jsonText" name="jsonText"
          rows="4" cols="2" placeholder="Cole seu json aqui8">
</textarea>

<pre id="json-renderer"></pre>

<script>
// self executing function here
    (()=> {
        
        $('#jsonText').on('input', ()=> {
            var data = {
            "firstName": "Jonh",
            "lastName": "Smith",
            "phones": [
                "123-45-67",
                "987-65-43"
                ]
            };

            $('#json-renderer').jsonViewer(data);    
        });

        
    })();
</script>

