# C4 Model and Mermaid

Using the excellent [C4 model](https://c4model.com/) to create diagrams in [mermaid](https://github.com/mermaid-js/mermaid).

All the templates have been prepared and tested with [Mermaid Live Editor](https://mermaid.live/).

## Level 1: Context 

```mermaid
graph LR
    %% C4 style classes c4model.com %%
    classDef person fill:#08427b,stroke:black,color:white;
    classDef software fill:#08427b,stroke:black,color:white;
    classDef existing fill:#999999,stroke:black,color:white;
    classDef boundary fill:white,stroke:black,stroke-width:2px,stroke-dasharray: 5 5;
    classDef frame fill:white,stroke:black;

    %% nodes %%
    Person((Person)):::person
    SoftwareSystem:::software
    ExistingSystem["Software System,<br>Existing System"]:::existing

    %% connections and boundaries %%
    
    subgraph Legend
        Person-.->|Relationship| SoftwareSystem
        subgraph Boundary
            SoftwareSystem-.->|Relationship| ExistingSystem
        end
        class Boundary boundary
    end
    class Legend frame
```

## Level 2: Container

Note: app and browser are containers too

```mermaid
graph LR
    %% C4 style classes c4model.com %%
    classDef person fill:#08427b,stroke:black,color:white;
    classDef container fill:#1168bd,stroke:black,color:white;
    classDef database fill:#1168bd,stroke:black,color:white;
    classDef software fill:#08427b,stroke:black,color:white;
    classDef existing fill:#999999,stroke:black,color:white;
    classDef boundary fill:white,stroke:black,stroke-width:2px,stroke-dasharray: 5 5;
    classDef frame fill:white,stroke:black;


    %% nodes %%
    Person((Person)):::person
    SoftwareSystem:::container
    ExistingSystem["Software System,<br>Existing System"]:::existing
    Database[(Database)]:::database

    %% connections and boundaries %%
    
    subgraph Legend
        Person-.->|Relationship| SoftwareSystem
        subgraph Boundary["Boundary: System under development"]
            SoftwareSystem-.->|Relationship| Database
        end
        class Boundary boundary
        SoftwareSystem-.->|Relationship| ExistingSystem
    end
    class Legend frame
```

## Level 3: Component
```mermaid
graph LR
    %% C4 style classes c4model.com %%
    classDef container fill:#1168bd,stroke:black,color:white;
    classDef component fill:#7ebced,stroke:black,color:white;
    classDef database fill:#1168bd,stroke:black,color:white;
    classDef software fill:#08427b,stroke:black,color:white;
    classDef existing fill:#999999,stroke:black,color:white;
    classDef boundary fill:white,stroke:black,stroke-width:2px,stroke-dasharray: 5 5;
    classDef frame fill:white,stroke:black;

    %% nodes %%
    Container["Other Container"]:::container
    Component:::component
    ExistingSystem["Software System,<br>Existing System"]:::existing
    Database[(Database)]:::database

    %% connections and boundaries %%
    
    subgraph Legend
        Container-.->|Relationship| Component
        subgraph Boundary["Boundary: Container"]
            Component
        end
        Component-.->|Relationship| ExistingSystem
        Component-.->Database
        class Boundary boundary
    end
    class Legend frame
```
