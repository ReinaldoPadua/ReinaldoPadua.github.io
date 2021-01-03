---
layout: tools
title: "Tools"
permalink: '/tools'
---
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<link href="{{ base.url | prepend: site.url }}/assets/css/json-viewer.css" rel="stylesheet" />
<link href="{{ base.url | prepend: site.url }}/assets/css/simpleXML.css" rel="stylesheet" />

<script src="{{ base.url | prepend: site.url }}/assets/libs/json-viewer.js"></script>
<script src="{{ base.url | prepend: site.url }}/assets/libs/simpleXML.js"></script>

<textarea id="inputText" name="inputText"
          rows="4" cols="2" placeholder="Paste your JSON | XML | YAML here!">
</textarea>

<pre id="json-renderer"></pre>
<div id="xml-viewer"></div>

<script>
// self executing function here
    $('#json-renderer').hide();
    $('#xml-viewer').hide();
    (()=> {
        
        $('#inputText').on('input', ()=> {
           
            switch ($('#inputText').val().charAt(0)) {
                case '{':
                    showJsonViewer($('#inputText').val());
                    break;
                case '[':
                    showJsonViewer($('#inputText').val());
                    break;
                case '<':
                    showXMLViewer($('#inputText').val());
                    break;
                default:
                    showYAMLViewer($('#inputText').val());
            }                    
        });

        
    })();

    const showJsonViewer = (inputText)=> {
        
        try{
            $('#json-renderer').jsonViewer(JSON.parse(inputText)); 
            $('#json-renderer').show();
        } catch(e) {
            $('#json-renderer').jsonViewer(''); 
            $('#json-renderer').hide();
        }
    }

     const showXMLViewer = (inputText)=> {
        
        try{

            const parser = new DOMParser();
            const dom = parser.parseFromString(inputText, "application/xml");
            console.log(dom.toXMLString())
            $("#xml-viewer").simpleXML({
	            xmlString: domXML
           }); 
            $('#xml-viewer').show();
        } catch(e) {
            $('#xml-viewer').hide();
        }
    }

</script>

