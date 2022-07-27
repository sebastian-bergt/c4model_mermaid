# c4model_mermaid

Using the excellent [C4 model](https://c4model.com/) to create diagrams in [mermaid](https://github.com/mermaid-js/mermaid).


## Context 

```mermaid
graph LR
    %% C4 classes c4model.com%%
    classDef person fill:#08427b,color:#FFF;
    classDef software fill:#1168bd,color:#FFF;
    classDef existing fill:#999999,color:#FFF;
    classDef boundary fill:#FFF,stroke:#000,stroke-width:2px,stroke-dasharray: 5 5;
    classDef frame fill:#FFF,stroke:#000

    subgraph Legend
        Person((Person)):::person-.->|Relationship| SoftwareSystem:::software
        subgraph Boundary
            SoftwareSystem-.->|Relationship| ExistingSystem["Software System,<br>Existing System"]:::existing
        end
        class Boundary boundary
    end
    class Legend frame
```

## 
