---
layout: tools
title: "Tools"
permalink: '/tools'
---
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<link href="{{ base.url | prepend: site.url }}/assets/css/json-viewer.css" rel="stylesheet" />
<script src="{{ base.url | prepend: site.url }}/assets/libs/json-viewer.js"></script>


<textarea id="jsonText" name="jsonText"
          rows="4" cols="2" placeholder="Paste your json here!">
</textarea>

<pre id="json-renderer"></pre>

<script>
// self executing function here
    $('#json-renderer').hide();
    (()=> {
        
        $('#jsonText').on('input', ()=> {
            let data = JSON.parse($('#jsonText').val());
            if(data.length>0){
                $('#json-renderer').jsonViewer(data);
                $('#json-renderer').show();
            } else $('#json-renderer').hide();
                
        });

        
    })();
</script>

