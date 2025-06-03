# Announcement model
The following manual describes how an announcement is configured on the ‘ePublication’ platform.
```mermaid

%%{
  init: {
    'theme': 'neutral'
  }
}%%

block-beta
columns 3

block:scope["standard"]:6

terms["<a href='https://github.com/officialgazette/announcement/blob/main/catalog.json'>terms
catalog

(JSON)</a>"]:1
space
standard["<a href='https://github.com/officialgazette/announcement/blob/main/types.xsd'>types

(XSD)</a>"]

end
space:5

config["<a href='https://github.com/officialgazette/announcement/blob/main/config-BP-default.json'>configuration of
announcement type

(JSON)</a>"]:2

space:4

schema["schema

(XSD/JSON)"]:2

config --"consists of"--> standard
config --"consists of"--> terms
config --"generates"--> schema





```
