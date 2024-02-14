AverageSum = 

    SUMX(
        VALUES(CONSUMPTION[GI_ITEMS]), // Groupby column name 
        CALCULATE(
            AVERAGE(CONSUMPTION[PRICE_PER_UNIT])
            )
)
