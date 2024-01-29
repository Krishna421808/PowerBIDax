// 0-30 days ageing
0-30 days=	
VAR maxdate =
    MAX ( Calender[Date] )
VAR mindate =
    MAX ( Calender[Date] ) - 30
VAR amt =
    CALCULATE (
        SUM ( detailVendorLedgerEntries[amountLCY] ),
        DATESBETWEEN (
            vendorLedgerEntries[postingDate],
            EDATE ( MAX ( Calender[Date] ), -1 ) + 1,
            MAX ( Calender[Date] )
        )
    )
RETURN
    amt
// 30-60 days ageing 
30-60 days=
VAR maxdate =
    EDATE (
        MAX ( Calender[Date] ),
        -2
    )
VAR amt =
    CALCULATE (
        SUM ( detailVendorLedgerEntries[amountLCY] ),
        DATESBETWEEN (
            vendorLedgerEntries[postingDate],
            EDATE ( MAX ( Calender[Date] ), -2 ) + 1,
            EDATE (
                MAX ( Calender[Date] ),
                -1
            )
        )
    )
RETURN
    amt     

// 60-90 days ageing

60-90 days= 
VAR maxdate =
    EDATE (
        MAX ( Calender[Date] ),
        -2
    )
VAR amt =
    CALCULATE (
        SUM ( detailVendorLedgerEntries[amountLCY] ),
        DATESBETWEEN (
            vendorLedgerEntries[postingDate],
            EDATE ( MAX ( Calender[Date] ), -3 ) + 1,
            EDATE (
                MAX ( Calender[Date] ),
                -2
            )
        )
    )
RETURN
    amt

// 90-120 days 
90-120 days=
VAR maxdate =
    EDATE (
        MAX ( Calender[Date] ),
        -2
    )
VAR amt =
    CALCULATE (
        SUM ( detailVendorLedgerEntries[amountLCY] ),
        DATESBETWEEN (
            vendorLedgerEntries[postingDate],
            EDATE ( MAX ( Calender[Date] ), -4 ) + 1,
            EDATE (
                MAX ( Calender[Date] ),
                -3
            )
        )
    )
RETURN
    amt
// 120 days or more ageing 
120 days or more= 
VAR maxdate =
    EDATE (
        MAX ( Calender[Date] ),
        -2
    )
VAR amt =
    CALCULATE (
        SUM ( detailVendorLedgerEntries[amountLCY] ),
        DATESBETWEEN (
            vendorLedgerEntries[postingDate],
            MIN ( Calender[Date] ),
            EDATE (
                MAX ( Calender[Date] ),
                -4
            )
        )
    )
RETURN
    amt
    
