# Customer-Analysis-Report
This is a  business customer analysis project
i created this report analyze customers based on certain criterias for better customer related decisions.
--------------------------------------------------------------------------------
here are some measures and columns i created to derive insights;
Age Bracket = 
SWITCH( TRUE(), 'Customer Overview Data'[Customer age] >= 3 && 'Customer Overview Data'[Customer age] <= 12, "Child", 
'Customer Overview Data'[Customer age] >= 13 && 'Customer Overview Data'[Customer age] <= 19, "Teenager",
'Customer Overview Data'[Customer age] >= 20 && 'Customer Overview Data'[Customer age] <= 30, "Young Adult", 
'Customer Overview Data'[Customer age] >= 31 && 'Customer Overview Data'[Customer age] <= 49, "Middle-Aged Adult", 'Customer Overview Data'[Customer age] >= 50 && 'Customer Overview Data'[Customer age] <= 80, "Old Adult", "other" )
--------------------------------------------------------------------------------
Customer age = YEAR(TODAY()) - 'Customer Overview Data'[Birth Year]
--------------------------------------------------------------------------------
Income Bracket = 
SWITCH(
    TRUE(),
    'Customer Overview Data'[Income] <= 50000, "0 - 50K",
    'Customer Overview Data'[Income] > 50000
    && 'Customer Overview Data'[Income] <= 100000, "50K - 100K",
    'Customer Overview Data'[Income] > 100000, "100K +",
    BLANK()
)
--------------------------------------------------------------------------------
no of customers = DISTINCTCOUNT('Customer Overview Data'[Customer ID])
--------------------------------------------------------------------------------
Purchase Recency Bracket = SWITCH(
    TRUE(),
    'Customer Overview Data'[Purchase Recency] <= 30, "0-30Days",
    'Customer Overview Data'[Purchase Recency] > 30
    && 'Customer Overview Data'[Purchase Recency] <= 60, "30-60Days",
    'Customer Overview Data'[Purchase Recency] > 60
    && 'Customer Overview Data'[Purchase Recency] <= 90, "60-90Days",
    'Customer Overview Data'[Purchase Recency] > 90
    && 'Customer Overview Data'[Purchase Recency] <= 120,"90-120Days",
    'Customer Overview Data'[Purchase Recency] > 120,"120Days +",
    BLANK()
)
