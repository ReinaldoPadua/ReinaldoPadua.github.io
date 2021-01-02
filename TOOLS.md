---
layout: tools
title: "Tools"
permalink: '/tools'
---
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<link href="{{ base.url | prepend: site.url }}/assets/css/json-viewer.css" rel="stylesheet" />
<script src="{{ base.url | prepend: site.url }}/assets/libs/json-viewer.js"></script>


<textarea id="inputText" name="inputText"
          rows="4" cols="2" placeholder="Paste your JSON | XML | YAML here!">
</textarea>

<pre id="json-renderer"></pre>

<script>
// self executing function here
    $('#json-renderer').hide();
    (()=> {
        
        $('#jsonText').on('input', ()=> {
            let inputText = $('#inputText').val();
            if(inputText!==undefined && inputText.length>0) {
                $('#json-renderer').jsonViewer(JSON.parse(inputText)); 
                $('#json-renderer').show() :
            }
            $('#json-renderer').jsonViewer(''); 
            $('#json-renderer').hide()
            
        });

        
    })();
</script>

