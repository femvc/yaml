yaml
====

A simple yaml parse engine. There is a example.

```    
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>YAML Parser</title>
    <script type="text/javascript" src="yaml.js"></script>
    <script type="text/javascript">
        window.onload = function() {
            var test1 = YAML.evalStr('Module_Name: BUI YAML - A simple yaml parse engine. ');
            alert(test1['Module_Name']);
            document.getElementById('test01').innerHTML = test1['Module_Name'];
            
            YAML.fromURL('example.yml', function(data) {
                var errors = YAML.getErrors();
                if(errors.length == 0) {
                    document.getElementById('test02').innerHTML = data['hi'];
                    //document.getElementById("out").innerHTML = "Done! Took " + YAML.getProcessingTime() 
                    + " miliseconds.";
                }
                else {
                    document.getElementById('test02').innerHTML = errors.join("<br>");
                }
            });
        };
    </script>
</head>
<body>
    <pre id="test01"></pre>
    <pre id="test02"></pre>
</body>
</html>
```