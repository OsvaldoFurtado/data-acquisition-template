Design
====================================================

.. uml:: 

    @startuml classes_DataAcquisition
    set namespaceSeparator none
    class "Extract" as src.csv_extract.Extract {
    builders : list[PairBuilder]
    build_pairs(row: list[str]) -> list[RawData]
    }
    class "PairBuilder" as src.csv_extract.PairBuilder {
    target_class : type[RawData]
    {abstract}from_row(row: list[str]) -> RawData
    }
    class "Series1Pair" as src.csv_extract.Series1Pair {
    target_class : XYPair
    from_row(row: list[str]) -> RawData
    }
    class "Series2Pair" as src.csv_extract.Series2Pair {
    target_class : XYPair
    from_row(row: list[str]) -> RawData
    }
    class "Series3Pair" as src.csv_extract.Series3Pair {
    target_class : XYPair
    from_row(row: list[str]) -> RawData
    }
    class "Series4Pair" as src.csv_extract.Series4Pair {
    target_class : XYPair
    from_row(row: list[str]) -> RawData
    }
    class "SomeOtherStructure" as src.model.SomeOtherStructure {
    x : list[str]
    y : list[str]
    }
    class "XYPair" as src.model.XYPair {
    x : str
    y : str
    }
    src.csv_extract.Series1Pair --|> src.csv_extract.PairBuilder
    src.csv_extract.Series2Pair --|> src.csv_extract.PairBuilder
    src.csv_extract.Series3Pair --|> src.csv_extract.PairBuilder
    src.csv_extract.Series4Pair --|> src.csv_extract.PairBuilder
    @enduml