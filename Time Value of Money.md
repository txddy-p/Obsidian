TVM refers to the concept that money today is worth more than money in future or R1 received today is worth more than R1 received after one year. Reasons for this include:
- Today’s money can be invested to earn interest.
- Today’s money can be spent before inflation reduces its buying power.
- Today’s money has no uncertainty regarding its receipt in future.
To make the right investment decision, `cash flows` occurring `at different times must` first be `adjusted` to reflect their `values at a single point in time` before they can be compared.
- Two methods of comparing CFs occurring at different times are:
- `Future value technique`: Uses `compounding` to find FV of each cash flow.
- `Present value technique`: Uses `discounting` to find PV of each cash flow.
![[compounding_discounting.png]]

## BASIC PATTERNS OF CASH FLOWS:
- Both cash outflows and inflows can be described by their patterns as follows:
- `Single amount`: A lump-sum received today or at a future date.
- `Annuity`: A stream (series) of equally spaced and level cash flows.
- `Mixed stream`: A stream of unequal periodic cash flows or a stream of cash flows that is not an annuity.
- `The principal`: Is the amount (original investment) on which interest is paid.
- `Simple interest`: Is the amount of interest paid on the original principal amount only.
- `Compound interest`: Consists of simple interest and interest-on-interest earned in a prior period.
###### FUTURE VALUE FORMULA/EQUATION (For LUMPSUM):
- $FV_n = PV \times (1 + i)^n$ Where:
- $FV_n$ = Future value of investment at the end of period n.
- PV = Present value or original principal.
- i = The interest rate per period, often a year, but can also be half-yearly, quarterly, monthly, weekly or daily. “r” is sometimes used.
- n = The number of periods. Sometimes denoted as “t”.
- $(1 + i)^n$ = The future value interest factor (FVIF). Given in tables.
###### COMPOUNDING MORE FREQUENTLY THAN ONCE A YEAR
- The more frequently the interest payments are compounded, the larger the future value of R1 for a given period. The formula is:
- ${FV}_n = {PV} x (1 + \frac{i}{m})^{nm}$ Where:
	- m = The number of compounding periods in a year. How many compounding periods per year if interest is paid: Yearly, Half yearly?Quarterly? Monthly? Weekly? Daily?
	- Note that banks quote an interest rate (i) as a nominal annual rate called the Annual Percentage Rate (APR).
- To calculate the `periodic interest rate`, divide the nominal interest rate or the APR by the number of compounding periods per year (m). $\text{Periodic interest} = \frac{APR}{m}$
- To calculate the `total number of periods`, multiply the number of years by the number of compounding periods per year. $\text{total periods} = n\times m$
##### The more frequent the compounding, the bigger the future value of an amount.

# Present Value & Discounting: Lump-sum
- PRESENT VALUE (PV) MEASURES WHAT ONE OR MORE CASH FLOWS RECEIVED IN FUTURE ARE WORTH TODAY (AT TIME t=0):
- The process of calculating the PV is called discounting and the interest rate “i” is known as the discount rate.
- The PV is often called the discounted value of future cash payments.
- THE PV FORMULA FOR A LUMP-SUM IS:
- $PV = FV \times (1+i)^{-n}$ or $PV = FV \times (1+\frac{i}{m})^{-nm}$
	- $(1+i)^{-n}$ or $(1+\frac{i}{m})^{-nm}$ gives you the present value interest factor (PVIF) provided in tables
	- The PVIF is the reverse of the FVIF
- PV Calculations show how much money you need today in order to achieve your financial goals in future. EXAMPLES.
- The further in the future the money will be received, the less it is worth today. TVM. Also, as “n” gets larger, the PVIF gets smaller.
- The higher the discount rate, the lower the present value of the money. As “i” gets larger, the PVIF gets smaller. 

# Effective Annual Interest Rate (EAR)
ANNUAL PERCENTAGE RATE (APR) AND PERIODIC RATE:
- In financial markets, interest rates can be quoted in a variety of ways. Examples are:
	- The annual percentage rate (APR) such as 12% per annum.
	- The periodic interest rate (e.g., 1% per month).
- The APR is the annualized interest rate using simple interest. It is annualized by multiplying the periodic rate by the number of compounding periods per year (APR = Periodic rate x m). How is the periodic interest rate calculated?
- The law requires banks to disclose the APR or the quoted interest rate, which is a nominal rate.
- Quoted interest rates are not comparable if the number of compounding periods per year are different. SOLUTION?
- The effective annual interest rate (EAR) enables us to compare “apples with apples” and make the correct financial decision.22
- EAR is the annual interest rate that takes compounding into account. It is the true cost of borrowing or actual return on an investment. 
- The formula for the EAR: $\text{EAR} = (1 +\frac{\text{APR}}{m})^m – 1$

# Annuities
- Equally spaced level stream of fixed cash flows for a limited period of time.
- `Cash Outflows`: Car & House loan, House, Education, Holiday, Saving for retirement. Watch out for Inflation!!
- `Cash Inflows`: Retirement annuity from pension fund or a purchased retirement annuity from financial services companies.
#### Ordinary Annuity
The cash payments (investments made) / receipts occur at the END of each period.
###### Future Value of an Ordinary Annuity (FVA)
$FVA_{Ord}$ = Instalment (I) or Payment (PMT) x Future Value Interest Factor for an annuity (FVIFA)
$$
FVA_{ord} = I \times FVIFA \text{ or } PMT \times FVIFA
$$
$$
{FVA}_{ord} = I \times \left [ \frac{(1+i/m)^{n\times m} - 1}{i/m} \right ]
$$
###### Present Value of an Ordinary annuity
$PVA_{ord}$ = Instalment (I) or Payment (PMT) x Present Value Interest Factor for an annuity (PVIFA)
$$
PVA_{ord} = I \times PVIFA \text{ or } PMT \times PVIFA
$$
$$
PVA_{Ord} = I \times \left [ \frac{(1 - (1+ i/m)^{-n\times m}}{i / m}\right ]
$$
Present Value of an Ordinary Annuity (PVA)
#### Annuity Due
The cash payments (investments made) / receipts occur at the BEGINNING of each period.
- There is no relationship between `Future Value Interest Factor of an Annuity` (`FVIFA`) and `Present Value Interest Factor of an Annuity` (`PVIFA`)
###### Future Value of Annuity Due (FVA)
$$
{FVA}_{Due} = I \times \left [ \frac{(1+i/m)^{n\times m} - 1}{i/m} \right ] \times ( 1 + i/m )
$$
###### Present Value of an Ordinary annuity
$$
PVA_{Due} = I \times \left [ \frac{(1 - (1+ i/m)^{-n\times m}}{i / m}\right ] \times ( 1 + i/m )
$$
I = instalment (cash payment / investment)
i = interest rate per period
n = number of years
m = number of compounding periods
# Perpetuities
#### Characteristics of Perpetuities
- Perpetuity is an annuity that has an indefinite lifespan.
- Useful to value investments such as property especially land and shares.
- Purchase asset today in exchange for receipt of an indefinite stream of payments in the future. I can only think of property that would provide an infinite stream of future cash flows.
- Perpetuity has no Future value (FV).
- So a Perpetuity has a Present value (PV).
$$
\text{(Present value) } PV = \frac{C}{r}
$$
Where:
- C = the constant amount received at the end of each period.
- r = the constant rate of return on the perpetuity.

### Valuation of an Ordinary share in a company
PV of an ordinary share ($P_0$ ) = $\frac{\text{Total Dividend}}{\text{Required rate of return}}$
- Dividend = Distribution of part of a company’s ANNUAL Net profits AFTER TAX on a semi-annual (Interim) or/and annual basis (Final) .
- Assumption is made that the Company will pay a dividend in perpetuity. 
- It does not really happen as companies sometimes cut/decrease their dividends to finance their future growth plans or to buy back shares.