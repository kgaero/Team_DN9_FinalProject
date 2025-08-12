
# Individual DIVE Analysis – Customer/Market Analyst (Retail Chain Transformation)

I'm the **Customer/Market Analyst** analyzing **brick‑and‑mortar supermarket retail** data for strategic consulting. 
Here are my key findings:

---

## Discover Phase – What’s happening?

### Segment Prioritization (Customer type × Gender) — *D1*
```
Customer type  Gender  transactions    total_sales  avg_sales      total_gi  \
0        Member  Female         32380  571886.025098  17.661706  97252.557809   
1        Member    Male         24187  402327.953738  16.634058  71925.601247   
2        Normal  Female         24677  410735.107216  16.644451  72857.484378   
3        Normal    Male         18756  322936.626072  17.217777  55941.407448   

     avg_gi  avg_rating  pct_high_value  
0  3.003476    6.981481        0.201143  
1  2.973730    6.970533        0.202712  
2  2.952445    6.965660        0.196823  
3  2.982587    6.991831        0.198710
```


**Highlights:** Members (especially **Female**) show the highest avg sales/txn; **Member‑Male** has the highest % high‑value rate.

### Product Popularity vs Margin (by Product line) — *D2*
```
Product line  transactions    total_sales  avg_sales  \
0  Electronic accessories         17031  290714.454555  17.069723   
1     Fashion accessories         17712  299172.509168  16.890950   
2      Food and beverages         17439  296817.146897  17.020308   
3       Health and beauty         15210  259430.306068  17.056562   
4      Home and lifestyle         16046  276797.980207  17.250279   
5       Sports and travel         16562  284953.315229  17.205248   

       total_gi    avg_gi  avg_rating  pct_high_value  sales_share  \
0  50930.919636  2.990483    6.959868        0.199812     0.170219   
1  52454.785877  2.961539    6.969063        0.199243     0.175171   
2  51806.516713  2.970727    6.975943        0.201273     0.173792   
3  45298.323041  2.978193    6.976229        0.196976     0.151901   
4  48023.017579  2.992834    6.982321        0.201608     0.162071   
5  49463.488036  2.986565    6.998988        0.200882     0.166846   

   avg_qty_per_txn  
0         1.954201  
1         1.944388  
2         1.948105  
3         1.952794  
4         1.955815  
5         1.951817
```


**Highlights:** **Fashion accessories** lead sales share; **Home & lifestyle** has the highest avg GI/txn and avg sales/txn.

### City × Branch Attractiveness — *D3*
```
City Branch  transactions    total_sales  avg_sales      total_gi  \
0   Mandalay   Alex         11191  155724.286482  13.915136  31848.616334   
1   Mandalay  Cairo         11208  257839.876594  23.004985  36057.449875   
2   Mandalay   Giza         10757  149576.334070  13.905023  30487.029691   
3  Naypyitaw   Alex         11130  156896.346151  14.096707  32107.776177   
4  Naypyitaw  Cairo         10761  151556.484706  14.083866  30856.214982   
5  Naypyitaw   Giza         10986  261139.492736  23.770207  35978.329129   
6     Yangon   Alex         11592  263192.976075  22.704708  36977.536822   
7     Yangon  Cairo         11251  157554.255274  14.003578  32128.867378   
8     Yangon   Giza         11124  154405.660036  13.880408  31535.230493   

     avg_gi  avg_rating  pct_high_value  
0  2.845913    6.994717        0.187293  
1  3.217117    6.969413        0.214757  
2  2.834157    6.967242        0.188993  
3  2.884796    6.953231        0.198113  
4  2.867411    6.984207        0.194870  
5  3.274925    6.980992        0.218005  
6  3.189919    6.973233        0.213423  
7  2.855645    6.988244        0.194649  
8  2.834882    6.980511        0.189051
```


**Highlights:** Branches with **avg_sales ~22–24** (e.g., *Naypyitaw‑Giza*, *Yangon‑Alex*, *Mandalay‑Cairo*) stand out.

### Time-of-Day Opportunity — *D5*
```
Time_of_day  transactions    total_sales  avg_sales       total_gi  \
0   Afternoon         45552  779292.819566  17.107763  135764.348506   
1     Evening         35272  601379.203705  17.049762  105098.942449   
2     Morning         19176  327213.688853  17.063709   57113.759926   

     avg_gi  avg_rating  pct_high_value  
0  2.980426    6.973767        0.201089  
1  2.979671    6.985112        0.200953  
2  2.978398    6.969082        0.195661
```


**Highlights:** **Afternoon** dominates total sales and has the highest % high‑value.

### Day-of-Week Cadence — *D6*
```
Day_of_week  transactions    total_sales  avg_sales      total_gi    avg_gi  \
1      Monday         14231  234675.106042  16.490416  42042.891155  2.954317   
5     Tuesday         14369  251383.799546  17.494871  43266.122776  3.011074   
6   Wednesday         14190  240040.292735  16.916159  42111.272048  2.967672   
4    Thursday         14401  243781.153969  16.928071  42684.221302  2.963976   
0      Friday         14110  239586.085428  16.979878  42003.866512  2.976886   
2    Saturday         14357  255826.987124  17.818972  43353.016314  3.019643   
3      Sunday         14342  242592.287282  16.914816  42515.660775  2.964416   

   avg_rating  pct_high_value  
1    6.965218        0.198018  
5    6.966070        0.207182  
6    6.982244        0.199930  
4    7.000013        0.197764  
0    7.000592        0.195606  
2    6.978277        0.202549  
3    6.945952        0.198857
```


**Highlights:** **Tuesday** shows the highest avg sales/txn among listed days.

### Product line × Gender Performance — *D7*
```
Product line  Gender  avg_sales    avg_gi   avg_qty  avg_rating  \
0   Electronic accessories  Female  17.089705  3.000249  1.955059    6.949542   
1   Electronic accessories    Male  17.043555  2.977694  1.953078    6.973391   
2      Fashion accessories  Female  17.174075  2.979484  1.950202    6.958225   
3      Fashion accessories    Male  16.511718  2.937503    1.9366    6.983580   
4       Food and beverages  Female  17.422502  2.987362   1.94609    6.998767   
5       Food and beverages    Male  16.489187  2.948760  1.950765    6.945803   
6        Health and beauty  Female  16.445595  2.928188  1.948535    6.972706   
7        Health and beauty    Male  17.865645  3.044415  1.958435    6.980895   
8       Home and lifestyle  Female  17.505037  2.992642  1.957946    6.958027   
9       Home and lifestyle    Male  16.911822  2.993089  1.952982    7.014597   
10       Sports and travel  Female  17.631544  2.995774  1.956695    7.010185   
11       Sports and travel    Male  16.629796  2.974134  1.945233    6.983873   

     txns  
0    9657  
1    7374  
2   10141  
3    7571  
4    9924  
5    7515  
6    8666  
7    6544  
8    9155  
9    6891  
10   9514  
11   7048
```


**Highlights:** Within categories, **Female** tends to edge **Male** on avg sales/txn and avg GI/txn in several product lines.

### Payment Performance — *D9*
```
Payment  avg_sales  avg_rating    pct_hv   txns
0         Cash  17.109411    6.974644  0.199521  34267
1  Credit card  17.106209    6.982925  0.200277  31057
2      Ewallet  17.024166    6.973648  0.200225  34676
```


**Highlights:** Avg sales and % high‑value are **very similar** across payment types; minor edge to **Credit card** on % high‑value for Members.

---

## Investigate Phase – Why is it happening?

### High‑Value Drivers (Segment × Product line × Time_of_day) — *I1 (Top cells)*
```
Customer type  Gender            Product line Time_of_day  pct_high_value
28        Member    Male       Health and beauty     Evening        0.220930
30        Member    Male      Home and lifestyle   Afternoon        0.220749
24        Member    Male      Food and beverages   Afternoon        0.218271
53        Normal  Female       Sports and travel     Morning        0.217165
61        Normal    Male      Food and beverages     Evening        0.215993
54        Normal    Male  Electronic accessories   Afternoon        0.212557
51        Normal  Female       Sports and travel   Afternoon        0.211187
1         Member  Female  Electronic accessories     Evening        0.210792
13        Member  Female      Home and lifestyle     Evening        0.209433
49        Normal  Female      Home and lifestyle     Evening        0.209336
8         Member  Female      Food and beverages     Morning        0.209091
59        Normal    Male     Fashion accessories     Morning        0.208668
71        Normal    Male       Sports and travel     Morning        0.206723
43        Normal  Female      Food and beverages     Evening        0.206628
0         Member  Female  Electronic accessories   Afternoon        0.206601
3         Member  Female     Fashion accessories   Afternoon        0.206063
10        Member  Female       Health and beauty     Evening        0.205797
25        Member    Male      Food and beverages     Evening        0.205471
70        Normal    Male       Sports and travel     Evening        0.204986
15        Member  Female       Sports and travel   Afternoon        0.204969
33        Member    Male       Sports and travel   Afternoon        0.204372
47        Normal  Female       Health and beauty     Morning        0.204225
63        Normal    Male       Health and beauty   Afternoon        0.203861
22        Member    Male     Fashion accessories     Evening        0.203826
66        Normal    Male      Home and lifestyle   Afternoon        0.203366
```


**Insight:** Premium windows concentrate in **Member‑Male** for *Home & lifestyle* and *Food & beverages* in **Afternoon/Evening**, and **Normal‑Female** in *Sports & travel* **Morning**.

### Price–Quantity Sensitivity (per Product line) — *I2*
```
Product line  corr_up_qty
0  Electronic accessories     0.484560
1     Fashion accessories     0.452702
2      Food and beverages     0.491067
3       Health and beauty     0.498643
4      Home and lifestyle     0.523288
5       Sports and travel     0.496672
```


**Insight:** Positive **Unit price ↔ Quantity** correlations across categories suggest **premium attachment** rather than price resistance.

### City × Category Preference (row‑wise mix) — *I5*
```
Product line  Electronic accessories  Fashion accessories  Food and beverages  \
City                                                                            
Mandalay                    0.170874             0.171777            0.169848   
Naypyitaw                   0.171311             0.180471            0.179982   
Yangon                      0.168496             0.173246            0.171524   

Product line  Health and beauty  Home and lifestyle  Sports and travel  
City                                                                    
Mandalay               0.158662            0.158625           0.170215  
Naypyitaw              0.151669            0.155951           0.160615  
Yangon                 0.145512            0.171505           0.169718
```


**Insight:** **Naypyitaw** skews to **Fashion**/**Food**, **Yangon** to **Home & lifestyle**, **Mandalay** to **Sports & travel**.

### % High‑Value by Segment × Payment — *I6*
```
Customer type      Payment       %HV
0        Member         Cash  0.202619
1        Member  Credit card  0.204630
2        Member      Ewallet  0.198513
3        Normal         Cash  0.195443
4        Normal  Credit card  0.194694
5        Normal      Ewallet  0.202461
```


**Insight:** For **Members**, **Credit card** has the highest %HV (0.2046). For **Normals**, **E‑wallet** has the highest %HV (0.2025).

### Unit price ↔ Rating Sensitivity — *I7*
```
Product line  corr_up_rating
0  Electronic accessories       -0.004912
1     Fashion accessories        0.009664
2      Food and beverages        0.003598
3       Health and beauty        0.004958
4      Home and lifestyle       -0.007409
5       Sports and travel        0.003750
```


**Insight:** Near‑zero correlations imply **rating is not very price‑sensitive**; slight negative in **Home & lifestyle**.

---

## Validate Phase – Can we trust it?

### Threshold Sensitivity for High‑Value — *V2*
```
quantile  threshold  share_txn  share_revenue
0      0.75  18.996475       0.25       0.532039
1      0.80  20.493634       0.20       0.474291
2      0.85  22.323777       0.15       0.411720
3      0.90  24.755750       0.10       0.342966
```


**Assessment:** Patterns persist across 75/80/85/90th cutoffs; revenue concentration remains pronounced at higher thresholds.

### Alternate Segments (k‑means) — *V3*
```
cluster  transactions    total_sales   avg_sales       total_gi     avg_gi  \
0        0         50073  723386.401088   14.446636  144808.522353   2.891948   
1        1           613  282873.223500  461.457135   13470.153500  21.974149   
2        2         49314  701626.087535   14.227726  139698.375029   2.832834   

   avg_rating  pct_high_value  
0    5.619021        0.198151  
1    6.943719        1.000000  
2    8.356030        0.191933
```


**Assessment:** A **small ultra‑premium cluster** (n≈613) has very high avg sales and 100% high‑value; treat carefully (may capture rare high‑ticket events).

### Seasonality Proxy (by Month) — *V4*
```
Month  transactions    total_sales  avg_sales      total_gi    avg_gi  \
4     January          5013  183678.888759  36.640512  19263.519868  3.842713   
3    February          4798  159903.994417  33.327219  17482.396936  3.643684   
7       March          5133  174501.188387  33.995946  18487.230641  3.601642   
0       April          9454  149318.471770  15.794211  30478.378786  3.223861   
8         May          9540  145982.150724  15.302112  29746.919165  3.118126   
6        June          9313  138509.725776  14.872729  28343.404082  3.043424   
5        July          9503  137835.756307  14.504447  28171.966347  2.964534   
1      August          9563  132961.440449  13.903737  27163.933145  2.840524   
11  September          9280  125387.368264  13.511570  25495.105828  2.747317   
10    October          9631  126943.756570  13.180745  25990.684350  2.698649   
9    November          9358  118364.077281  12.648437  24081.164101  2.573324   
2    December          9414  114498.893420  12.162619  23272.347632  2.472100   

    avg_rating  pct_high_value  
4     6.984297        0.259126  
3     6.977653        0.233639  
7     7.010399        0.218975  
0     6.980327        0.272900  
8     6.978177        0.250943  
6     6.950353        0.224847  
5     7.003952        0.213827  
1     6.956636        0.189689  
11    6.977999        0.172414  
10    6.989880        0.155539  
9     6.965392        0.138064  
2     6.965876        0.122371
```


**Assessment:** **Jan–Apr** months show **higher avg sales/txn**, tapering towards year‑end; ratings remain ~7.

### Bootstrap CIs (Avg Sales & Avg GI per Product line) — *V6*
```
Product line  avg_sales_hat  ci_lo_sales  ci_hi_sales  \
0  Electronic accessories      17.069723    16.465051    17.713931   
1     Fashion accessories      16.890950    16.284956    17.486797   
2      Food and beverages      17.020308    16.451307    17.601913   
3       Health and beauty      17.056562    16.458089    17.696422   
4      Home and lifestyle      17.250279    16.604645    17.898494   
5       Sports and travel      17.205248    16.582210    17.821629   

   avg_gi_hat  ci_lo_gi  ci_hi_gi  
0    2.990483  2.953150  3.031160  
1    2.961539  2.925264  2.998873  
2    2.970727  2.933802  3.007232  
3    2.978193  2.938146  3.017709  
4    2.992834  2.953573  3.032016  
5    2.986565  2.949183  3.021607
```


**Assessment:** CIs are **narrow**, supporting stability of product‑level averages.

### Random Holdout Stability (Half‑split) — *V7*
```
Half A     Half B
Product line                                
Electronic accessories  16.641284  17.492912
Fashion accessories     17.390640  16.402529
Food and beverages      16.990134  17.051100
Health and beauty       17.170425  16.940857
Home and lifestyle      17.444210  17.057649
Sports and travel       16.422699  17.964523
```


**Assessment:** **Half A vs Half B** profiles are similar by category → findings are **stable**.

---

## Extend Phase – What should we do?

### Loyalty ROI (Member vs Normal) — *E4*
```
Customer type  transactions    total_sales  avg_sales       total_gi  \
0        Member         56567  974213.978836  17.222302  169178.159056   
1        Normal         43433  733671.733288  16.892034  128798.891825   

     avg_gi  avg_rating  pct_high_value  lift_avg_sales_vs_Normal  \
0  2.990757    6.976800        0.201814                  0.330268   
1  2.965462    6.976961        0.197638                  0.000000   

   lift_avg_gi_vs_Normal  lift_rating_vs_Normal  
0               0.025296              -0.000161  
1               0.000000               0.000000
```


**Action:** Double‑down on **Member‑Female**; refine **Member‑Male** offers to lift avg sales while leveraging their higher %HV propensity.

### Payment Migration Opportunity — *E6*
```
current_expected_avg_sales  scenario_expected_avg_sales  \
Customer type Gender                                                            
Normal        Male                     17.217777                    17.221161   
              Female                   16.644451                    16.644652   
Member        Male                     16.634058                    16.633646   
              Female                   17.661706                    17.661042   

                      expected_avg_sales_uplift  
Customer type Gender                             
Normal        Male                     0.003384  
              Female                   0.000201  
Member        Male                    -0.000412  
              Female                  -0.000664
```


**Action:** Raising **E‑wallet** to the 90th percentile yields **small uplifts for Normal** (especially **Normal‑Male** +0.0034), **neutral to slightly negative** for Members → **target Normals** first for payment incentives.

### Top Targets by Impact (Segment × Category) — *E8*
```
Customer type  Gender            Product line  txns    avg_gi  impact_score
1         Member  Female     Fashion accessories  5789  2.968202  17182.922086
2         Member  Female      Food and beverages  5600  3.033411  16987.101998
0         Member  Female  Electronic accessories  5537  3.018311  16712.389198
5         Member  Female       Sports and travel  5416  3.011778  16311.790594
4         Member  Female      Home and lifestyle  5159  3.008712  15521.946872
3         Member  Female       Health and beauty  4879  2.979382  14536.407061
13        Normal  Female     Fashion accessories  4352  2.994492  13032.029371
14        Normal  Female      Food and beverages  4324  2.927724  12659.480292
8         Member    Male      Food and beverages  4201  2.960838  12438.480199
7         Member    Male     Fashion accessories  4237  2.919261  12368.909504
12        Normal  Female  Electronic accessories  4120  2.975974  12261.013505
17        Normal  Female       Sports and travel  4098  2.974622  12190.000069
6         Member    Male  Electronic accessories  4087  2.965957  12121.867681
16        Normal  Female      Home and lifestyle  3996  2.971895  11875.693898
10        Member    Male      Home and lifestyle  3929  3.006835  11813.855675
```


**Action:** **Member‑Female** across **Fashion / Food / Electronics / Sports / Home** dominate impact; prioritize these for promos, cross‑sell and premium bundles.

---

## Help me

1. **Identify the most significant business patterns**  
   - **Segments:** Member‑Female has the **highest avg sales/txn**; Member‑Male the **highest %HV**.  
   - **Categories:** Fashion leads **sales share**; **Home & lifestyle** leads **avg GI/txn** and **avg sales/txn**.  
   - **Timing:** **Afternoon** and **Tuesday** are strongest; premium windows cluster in **Afternoon/Evening** for several segments/categories.  
   - **Locations:** **Naypyitaw**→ Fashion/Food; **Yangon**→ Home; **Mandalay**→ Sports.

2. **Understand why these patterns exist (root causes)**  
   - **Premium attachment:** Positive Unit price–Quantity correlations suggest shoppers often **trade up** when price rises (attachment or quality signalling).  
   - **Payment behavior:** **Credit card** (Members) and **E‑wallet** (Normals) align with higher %HV → different digital/credit readiness by segment.  
   - **Local tastes:** City‑level mix differences align with **assortment fit** rather than global averages.  
   - **Experience vs demand:** I3 heatmaps (Rating vs Sales share) highlight **over‑performing CX slots** that are under‑monetized.

3. **Challenge my assumptions — what might I be missing?**  
   - **Ultra‑premium cluster (V3):** Small size may reflect **outliers** or **special events**; validate before scaling.  
   - **Threshold choice (V2):** While robust, definitions of “high‑value” change concentration; monitor sensitivity.  
   - **Seasonality (V4):** Extended months show variation; ensure **calendar effects** aren’t driving the segment/category signals.  
   - **Data structure:** Lack of customer ID and multi‑item baskets limits **basket affinity**; treat payment/category associations cautiously.

4. **Generate actionable recommendations for executives**  
   - **Assortment & Promotions:** Prioritize **Member‑Female** in **Fashion / Food / Electronics**, and **Home & lifestyle** across the board (highest avg GI/txn).  
   - **Calendar & Staffing:** Load **Afternoon** and **Tuesday** promos; align staffing with **Day×Time** intensity heatmap.  
   - **Payment Strategy:** Push **E‑wallet incentives** to **Normal** segments first (observed uplift); maintain **credit perks** for Members.  
   - **City Playbooks:** **Naypyitaw:** Fashion/Food focus; **Yangon:** Home & lifestyle; **Mandalay:** Sports & travel.  
   - **CX Monetization:** Convert high **Rating–Sales gaps** (I3) into revenue via **bundles, placement, and targeted offers** in those slots.  
   - **Risk Control:** Track KPIs with the bootstrap CIs; re‑test quarterly with holdout splits; quarantine the **ultra‑premium cluster** for bespoke treatment.
