**Source**: https://www.youtube.com/watch?v=qI_g07C_Q5I
**Author**: #[[Martin Fowler]]
 **Tags**: #[[NoSQL]] #talks

- SQL problems
    - Impedance Mismatch
- Definition of NoSQL
    - non-relational
    - cluster-friendly
    - most tool open-source
    - schema-less 
    - Data models
         ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fmy-philosophy%2FZEcXoBWztw.png?alt=media&token=6098b0f5-3a37-4677-9135-4fc5a7033c61)
        - Aggregate-Oriented
            - Aggregate -> Book **Domain-Driven Design** #[[Books to Read]]
                - group thing together into natural aggregates
            - **Types**
                - Key-value store
                    - value == Aggregate
                - Document
                    - JSON (or XML) objects
                    - Document == Aggregate
                - Column - family
            - Not aggregate orientated
                - Types
                    - Graph
- aggregate oritentation
    - Benefits
        - Running in clusters efficiently way more straightforward
        - when most of the time we use the same aggregate to push data back and forward into persistence
    - Problems
        - slice and dice your data in different ways
- Consistency
