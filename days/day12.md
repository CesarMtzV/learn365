# Yara - TryHackMe
___
Index | Topic
--- | ---
**1** | Description
**2** | Yara rules
**3** | Other Yara rules


## Description

- Yara can identify information based on both binary and textual patterns, such as hex and strings contained within a file.
- Rules are used to label these pattern

## Yara rules

- Every yara command requires two arguments to be valid:
  - The rule file we create
  - Name of file, directory, or process ID to use the rule for
  - Example: `yara myrule.yar somedirectory`
- Some yara conditions:
  - Keyword
  - Desc
  - Meta
  - Strings
  - Conditions
  - Weight
- Example of searching a string in a file
```yar
rule helloworld_checker{
  strings:
    $hello_world = "Hello World!"
    $hello_world_uppercase = "HELLO WORLD"
    $hello_world_lowercase = "hello world"
  condition:
    any of them
}
```
- yara keyowrds:
  - and
  - not
  - or
  - Examples:
  ```yara
    rule hellowolrd_textfile_checker {
      strings:
        $hello_world = "Hello World!"
        $txt_file = ".txt"
      conditon:
        $hello_world and $txt_file
    }
  ```

## Other yara tools

- LOKI
- THOR
- FENRIR
- YAYA