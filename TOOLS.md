---
layout: default
title: "Tools"
permalink: '/tools'
---
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="{{ base.url | prepend: site.url }}/assets/libs/jsonlint.js"></script>
<script src="{{ base.url | prepend: site.url }}/assets/libs/jsonviewer.js"  type="module"></script>
<link href="{{ base.url | prepend: site.url }}/assets/css/jsonViewer.css" rel="stylesheet" />
<script src="{{ base.url | prepend: site.url }}/assets/libs/jsonViewer.js"></script>


<textarea id="jsonText" name="jsonText"
          rows="4" cols="2" placeholder="Cole seu json aqui4">
</textarea>

<div id="wrapper"></div>

<script>
// self executing function here
    (()=> {
        
        $('#jsonText').on('input', ()=> {
            // console.log($('#jsonText').val())
            // const jsonParsed = jsonlint.parse($('#jsonText').val());
            // console.log(jsonParsed);
            // new JsonViewer({
            //     container: document.body, 
            //     data: jsonParsed, 
            //     theme: 'light', 
            //     expand: false
            // });
        });

        var wrapper = document.getElementById("wrapper");

        // Get json-data by javascript-object
        var data = {
            "firstName": "Jonh",
            "lastName": "Smith",
            "phones": [
                "123-45-67",
                "987-65-43"
            ]
        };

        // or from a string by JSON.parse(str) method
        var dataStr = '{ "firstName": "Jonh", "lastName": "Smith", "phones": ["123-45-67", "987-65-43"]}';
        try {
            var data = JSON.parse(dataStr);
        } catch (e) {}

        // Create json-tree
        var tree = jsonTree.create(data, wrapper);

        // Expand all (or selected) child nodes of root (optional)
        tree.expand(function(node) {
        return node.childNodes.length < 2 || node.label === 'phoneNumbers';
        });



       
    })();
</script>

