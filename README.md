# Announcement model
The following sections describe the announcement model for a publication on ePublication.ch
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

The configuration is based on three artefacts:
- The data types
- The technical expressions
- The configuration of an announcement type

Each announcement type (synonymous with entry form on the GUI) consists of various elements (representing one or more input fields on the form).

**The data types**

The data type set is stored statically in the system and cannot be changed.

The set of data types is 

**The technical expresions**

xx

**The configuration of an announcement type**

xx
