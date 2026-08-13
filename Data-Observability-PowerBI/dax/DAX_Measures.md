# DAX Measures

## NullAmountCount
```DAX
NullAmountCount = 
CALCULATE(
    COUNTROWS(DataObservability_Mock),
    ISBLANK(DataObservability_Mock[Amount])
)
```

Counts records where `Amount` is blank.

## SchemaHealth
```DAX
SchemaHealth = 
IF(
    [NullAmountCount] > 0,
    "Issue Found",
    "All Good"
)
```

Converts the null-value check into a simple health status.

## SchemaNote
```DAX
SchemaNote = 
IF(
    [NullAmountCount] > 0,
    "Schema anomalies found. Please check the file(s).",
    "No schema issues detected. All good."
)
```

Provides a human-readable explanation of the health status.

## NullAmountPerFile
```DAX
NullAmountPerFile = 
CALCULATE(
    COUNTROWS(
        FILTER(
            DataObservability_Mock,
            ISBLANK(DataObservability_Mock[Amount])
        )
    ),
    ALLEXCEPT(
        DataObservability_Mock,
        DataObservability_Mock[FileDate]
    )
)
```

Counts missing `Amount` values while retaining the `FileDate` context.
