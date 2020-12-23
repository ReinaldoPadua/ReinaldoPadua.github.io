---
layout: default
title: "Tools"
permalink: '/tools'
---
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="{{ base.url | prepend: site.url }}/assets/libs/jsonlint.js"></script>

<textarea id="jsonText" name="jsonText"
          rows="4" cols="2" placeholder="Cole seu json aqui">
</textarea>

<script>
// self executing function here
    (()=> {

        import JsonViewer from './jsonViewer';

        $('#jsonText').on('input', ()=> {
            const jsonParsed = jsonlint.parse('{"creative?": false}');
            new JsonViewer({
                container: document.body, 
                data: jsonParsed, 
                theme: 'light', 
                expand: false
            });
        });
       
    })();
</script>

