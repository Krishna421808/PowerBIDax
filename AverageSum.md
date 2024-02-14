AverageSum = 

    SUMX(
        VALUES(CONSUMPTION[GI_ITEMS]), // Groupby column name 
        CALCULATE(
            AVERAGE(CONSUMPTION[PRICE_PER_UNIT])
            )
)

MaxSum = 

    SUMX(
        VALUES(CONSUMPTION[GI_ITEMS]), // Groupby column name 
        CALCULATE(
            Max(CONSUMPTION[PRICE_PER_UNIT])
            )
)

MinSum = 

    SUMX(
        VALUES(CONSUMPTION[GI_ITEMS]), // Groupby column name 
        CALCULATE(
            Min(CONSUMPTION[PRICE_PER_UNIT])
            )
)

