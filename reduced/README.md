# Announcement Model
## value-types.xsd ##
Describes the statically implemented value types. Created in a reduced version for prototyping purposes.
erDiagram

  Announcement ||--o{ BusinessCase : "uses"
  BusinessCase ||--o{ BusinessCaseCategory : "has"

  Announcement {
    string notice
    date deadline
    date publicationDate
    stringMultiline legalRemedy
    string description
    string themes
    number publicationPrice
    number publicityPeriod
    boolean archive
    string organisationType
    boolean livePublication
    boolean reaction
    boolean privacyRestrictions
    string gazette
    string action
  }

  Announcement }o--|| Person : "pointOfContact"
  Announcement }o--|| LegalPerson : "transferringCompany"
  Announcement }o--o{ LegalPerson : "acquiringCompany"

  Person {
    string name
    string firstName
    string organisation
  }

  Person }o--|| Address : "lives at"

  LegalPerson {
    string legalForm
    string name
    string UID
  }

  LegalPerson }o--|| Address : "located at"

  Address {
    string street
    string city
    string postalCode
  }

  BusinessCaseCategory {
    string key
    string label_de
    string label_fr
    string label_it
    string label_en
  }
