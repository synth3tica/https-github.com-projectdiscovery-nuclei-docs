### Helper Functions Examples

Nuclei has a number of helper functions that may be used to conduct various run-time operations on the request block. Here's an example template that shows how to use all the available helper functions.

```yaml
id: helper-functions-examples

info:
  name: RAW Template with Helper Functions
  author: pdteam
  severity: info

requests:
  - raw:
      - |
        GET / HTTP/1.1
        Host: {{Hostname}}
        01: {{base64("Hello")}}
        02: {{base64(1234)}}
        03: {{base64_decode("SGVsbG8=")}}
        04: {{base64_py("Hello")}}
        05: {{contains("Hello", "lo")}}
        06: {{generate_java_gadget("commons-collections3.1", "wget http://{{interactsh-url}}", "base64")}}
        07: {{gzip("Hello")}}
        08: {{hex_decode("6161")}}
        09: {{hex_encode("aa")}}
        10: {{html_escape("<body>test</body>")}}
        11: {{html_unescape("&lt;body&gt;test&lt;/body&gt;")}}
        12: {{len("Hello")}}
        13: {{len(5555)}}
        14: {{md5("Hello")}}
        15: {{md5(1234)}}
        16: {{mmh3("Hello")}}
        17: {{print_debug(1+2, "Hello")}}
        18: {{rand_base(5, "abc")}}
        19: {{rand_base(5)}}
        20: {{rand_char("abc")}}
        21: {{rand_char()}}
        22: {{rand_int(1, 10)}}
        23: {{rand_int(10)}}
        24: {{rand_int()}}
        25: {{rand_text_alpha(10, "abc")}}
        26: {{rand_text_alpha(10)}}
        27: {{rand_text_alphanumeric(10, "ab12")}}
        28: {{rand_text_alphanumeric(10)}}
        29: {{rand_text_numeric(10, 123)}}
        30: {{rand_text_numeric(10)}}
        31: {{regex("H([a-z]+)o", "Hello")}}
        32: {{remove_bad_chars("abcd", "bc")}}
        33: {{repeat("../", 5)}}
        34: {{replace("Hello", "He", "Ha")}}
        35: {{replace_regex("He123llo", "(\\d+)", "")}}
        36: {{reverse("abc")}}
        37: {{sha1("Hello")}}
        38: {{sha256("Hello")}}
        39: {{to_lower("HELLO")}}
        40: {{to_upper("hello")}}
        41: {{trim("aaaHelloddd", "ad")}}
        42: {{trim_left("aaaHelloddd", "ad")}}
        43: {{trim_prefix("aaHelloaa", "aa")}}
        44: {{trim_right("aaaHelloddd", "ad")}}
        45: {{trim_space("  Hello  ")}}
        46: {{trim_suffix("aaHelloaa", "aa")}}
        47: {{unix_time(10)}}
        48: {{url_decode("https:%2F%2Fprojectdiscovery.io%3Ftest=1")}}
        49: {{url_encode("https://projectdiscovery.io/test?a=1")}}
        50: {{wait_for(1)}}
```