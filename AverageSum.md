AverageSum = 
CALCULATE(
    SUMX(
        VALUES(CONSUMPTION[GI_ITEMS]), // Groupby column name 
        AVERAGE(CONSUMPTION[PRICE_PER_UNIT])
    ),
    CONSUMPTION[Table] = "CONSUMPTION" // if any filter
)
