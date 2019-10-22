- value proposition
  - seamless interchage between DCC 
  - distributed workflow
  - allow users to define high level semantics
  - provide superior read performance
  - provide superior tools for debugging and inspecting scenes
- What is USD?
  - A set of file formats, ascii and binary(named crate) 
  - A closed grammar of composition operators 
  - A set of consistent, high performance C++/Python libraries for interacting with USD assets 
  - A set of tools for understanding and modifying USD assets
- USD Terminology
  - Stage is made up of layers, connected by composition arcs 
  - Layers are composed of prims and properties, and also contain composition arcs 
    - Objects=Prims+Properties, objects in USD are identified by scene paths(sdf)
      - Prims: named conteainer of data(specifier+optional typename)
        - Typenames are defined in schemas, which has semantic meaning
      - Properties are composed of attributes or relationships
        - Attribute values can be time sampled and/or default valued.
        - Relationships are pointers to other prims
          - a mesh points to another material system
        - Metadata can be authored on prims and properties, and can not be time varying
  - Composition arcs
    - Operators for combining individual units of scene description
      - Local Values + Sublayers -> Inherits -> Variant Sets -> References -> Payloads -> Specializes
    - Sublayers defined as a list of asset paths pointing to other layers
      - Work as photoshop layers, from top to down
    - References
      - Used for composing smaller units of scene description together
      - One of the most commonly used composition arcs in practice
    - Payloads
      - Very similar to references
      - Not eagerly loaded by composition
      - Can be loaded after initial composition
    - Variant sets
      - Allow a distinct set of options, from which downstream clients can select
      - Can be considered like a switchable reference
- Extendability
  - USD provides many points at which you can extend the system to fit your pipeline:
    - Asset Resolution Plugins, File Format Plugins, Schemas, Usdview Plugins
  - Asset Resolution Plugins
    - translate file refereces to real paths
  - File format plugins
    - usd allows users to define file format plugins, whihc enables a scene to read geometry in from foreign sources
  - Schemas
    - These allow users to define higher level concepts on top of prims and properties
  - Hydra
    - The imaging system backing USD, not a GL system
    - Allows for multiple backend implementations
  - usdview
    - Fast preview application for USD scenes
    
    
  
  
  

