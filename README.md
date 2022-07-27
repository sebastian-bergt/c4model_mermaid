# c4model_mermaid

Using the excellent [C4 model](https://c4model.com/) to create diagrams in [mermaid](https://github.com/mermaid-js/mermaid).


## Context 

```mermaid
graph LR
    %% C4 style classes c4model.com %%
    classDef person fill:#08427b,stroke:#000,color:#FFF;
    classDef software fill:#1168bd,stroke:#000,color:#FFF;
    classDef existing fill:#999999,stroke:#000,color:#FFF;
    classDef boundary fill:#FFF,stroke:#000,stroke-width:2px,stroke-dasharray: 5 5;
    classDef frame fill:#FFF,stroke:#000

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

## Container

Note: app and browser are containers too

```mermaid
graph LR
    %% C4 style classes c4model.com %%
    classDef person fill:#08427b,stroke:#000,color:#FFF;
    classDef container fill:#1168bd,stroke:#000,color:#FFF;
    classDef database fill:#1168bd,stroke:#000,color:#FFF;
    classDef existing fill:#999999,stroke:#000,color:#FFF;
    classDef boundary fill:#FFF,stroke:#000,stroke-width:2px,stroke-dasharray: 5 5;
    classDef frame fill:#FFF,stroke:#000

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

## Component
```mermaid
graph LR
    %% C4 style classes c4model.com %%
    classDef container fill:#1168bd,stroke:#000,color:#FFF;
    classDef component fill:#7ebced,stroke:#000,color:#FFF;
    classDef database fill:#1168bd,stroke:#000,color:#FFF;
    classDef existing fill:#999999,stroke:#000,color:#FFF;
    classDef boundary fill:#FFF,stroke:#000,stroke-width:2px,stroke-dasharray: 5 5;
    classDef frame fill:#FFF,stroke:#000

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
