# Announcement Model
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

config --"contains"--> standard
config --"contains"--> terms
config --"generates"--> schema

```

The configuration is based on three artefacts:
- The data types
- The terms catalog
- The configuration of an announcement type

Each announcement type (synonymous with entry form on the GUI) consists of various elements (representing one or more input fields on the form).

## The data types ##

The data type set consists of complex and simple data types. Complex data types are:
- person (can be natural or legal persons)
- natural person
- legal person
- address
- dateFromTo

Simple types are:
- string
- int
- date
- duration
- time

> [!NOTE]
> The data type set is stored statically in the system and cannot be changed.

### The Business Rules ###

The static types can contain general business cases and constraints. These are continuously supplemented and described here.

**Legal Person**

Business Rule "Mandatory UID" in Legal Person:
Under certain circumstances, the UID number is mandatory for legal persons. The following flowchart describes in which cases a UID number is mandatory.

```mermaid


%%{
  init: {
    'theme': 'neutral'
  }
}%%

flowchart TD
    A[get legal person] --> B{no UID}
    B -- true --> C[legal form mandatory]
    C --> D{legal form}
    D -- "0106 / 0107 / 0108" --> E[UID mandatory / 'no UID' must be false]
    D -- "Other legal forms (eCH-0097)" --> F[UID not mandatory]
    B -- false --> G[legal form not mandatory]
    G --> H[UID mandatory]
```



## The terms catalog ##

The catalog of terms contains all specialized terms related to official announcements. The structure of the catalog is very straightforward and consists only of a key and a general description of the term.
However, the list is conclusive, which means that if, for example, announcements are imported via the API, only elements with a valid key can be imported.

## The configuration of an announcement type ##

The configuration of a notification type contains all necessary configurations and defines the actual content of a notification (in the form of a business case).
In the configuration of the business case, elements are defined using terms from the term catalog and typed using the types from the type schema.
