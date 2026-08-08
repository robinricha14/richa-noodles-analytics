# DAX Measures — NoodlesCrypto Top Performers

## Core Engagement Metrics

### Total Engagements
Total Engagements =
SUM(vw_ExecutiveDashboard[TotalEngagements])

### Total Likes
Total Likes =
SUM(vw_ExecutiveDashboard[TotalLikes])

### Total Comments
Total Comments =
SUM(vw_ExecutiveDashboard[TotalComments])

### Total Retweets
Total Retweets =
SUM(vw_ExecutiveDashboard[TotalRetweets])

### Avg Engagement Score
Avg Engagement Score =
AVERAGE(vw_ExecutiveDashboard[AvgEngagementScore])

### Distinct Currency Count
Distinct Currency Count =
DISTINCTCOUNT(DimCurrency[Symbol])

---

## Engagement Ratios

### Engagement per Post
Engagement per Post =
DIVIDE(
    [Total Engagements],
    SUM(vw_TimeSeries[TotalPosts]),
    0
)

---

## Time Intelligence Measures

### Engagement Today
Engagement Today =
CALCULATE(
    [Total Engagements],
    LASTDATE(DimDate[FullDate])
)

### Engagement Yesterday
Engagement Yesterday =
CALCULATE(
    [Total Engagements],
    DATEADD(DimDate[FullDate], -1, DAY)
)

### Engagement Change %
Engagement Change % =
DIVIDE(
    [Engagement Today] - [Engagement Yesterday],
    [Engagement Yesterday],
    0
)

### Engagement 7D Avg
Engagement 7D Avg =
CALCULATE(
    [Total Engagements],
    DATESINPERIOD(
        DimDate[FullDate],
        MAX(DimDate[FullDate]),
        -7,
        DAY
    )
)

### Engagement 30D Avg
Engagement 30D Avg =
CALCULATE(
    [Total Engagements],
    DATESINPERIOD(
        DimDate[FullDate],
        MAX(DimDate[FullDate]),
        -30,
        DAY
    )
)

---

## Ranking & Indicators

### Engagement Rank
Engagement Rank =
RANKX(
    ALL(DimCurrency[Symbol]),
    [Total Engagements],
    ,
    DESC,
    Dense
)

### Engagement Trend Label
Engagement Trend =
IF(
    [Engagement 7D Avg] > [Engagement 30D Avg],
    "Up ▲",
    "Down ▼"
)

---

## Platform Analysis

### Engagement by Platform
Engagement by Platform =
SUM(vw_SocialAnalytics[TotalEngagements])

### Platform Engagement Share %
Platform Engagement Share % =
DIVIDE(
    [Engagement by Platform],
    CALCULATE(
        [Engagement by Platform],
        ALL(vw_SocialAnalytics[PlatformName])
    ),
    0
)

---

## KPI Flags

### High Engagement Flag
High Engagement Flag =
IF([Total Engagements] >= 10000, 1, 0)
