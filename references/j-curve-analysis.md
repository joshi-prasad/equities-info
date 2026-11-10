# Understanding J-Curve analysis: From accounting ratios to business economics

The best way to understand your two Excel models is to think of J-Curve analysis as an attempt to answer one fundamental question:

Is the company converting incremental investments into progressively higher operating profits and returns?

This is different from simply asking whether revenue, EBITDA or PAT is growing.

A company can report 30% revenue growth and still destroy shareholder value if it needs disproportionately more capital to generate that growth.

Conversely, a company can experience temporarily weak ROCE and ROIC because it has invested heavily in new capacity that has not yet started generating revenue. That is precisely where J-Curve analysis becomes useful.

I inspected both your Sansera and Anthem spreadsheets. Your models already contain most of the important building blocks. I would, however, make a few distinctions between what the ratios measure, how they help identify the J-Curve, and some formula-related improvements.

Let's build the understanding from first principles.

## 1. First, understand what the J-Curve actually represents

Imagine a manufacturing company investing ₹500 crore in a new factory.

The investment happens today, but the revenue from that factory comes gradually:

1. First, the company spends money on land, buildings and machinery.
2. The factory is under construction. Revenue contribution is almost zero.
3. The factory is commissioned, but utilization is low.
4. Customer orders increase and utilization improves.
5. Fixed costs get absorbed over higher production volumes.
6. Profitability and return on invested capital improve.

The financial return can initially decline and subsequently rise sharply.

Illustrative J-Curve

Illustrative economic return trajectory, not actual Sansera or Anthem data.

The important point: the investment happens before the financial benefits become visible.

Therefore, you need to track both sides:

- Capital invested: How much money has the company committed?
- Returns generated: How much additional operating profit is that capital producing?

Your spreadsheets are trying to measure exactly this.

# 2. NOPAT and NOPAT Margin

Let's start with NOPAT because it is the foundation for understanding ROIC.

## What is NOPAT?

NOPAT stands for Net Operating Profit After Tax.

In simple language:

NOPAT tells you how much profit the actual business operations generate after tax, without considering how the business is financed.

Consider a hypothetical company:

| Particulars  | Amount    |
| ------------ | --------- |
| Revenue      | ₹1,000 Cr |
| EBITDA       | ₹200 Cr   |
| Depreciation | ₹50 Cr    |
| EBIT         | ₹150 Cr   |
| Tax rate     | 25%       |
| NOPAT        | ₹112.5 Cr |

The calculation:

\\[ NOPAT=EBIT\times(1-Tax\ Rate) \\]

\\[ =150\times(1-25\\%)=₹112.5Cr \\]

Why do we use EBIT instead of PAT?

Because PAT is affected by interest expenses and financing decisions.

Imagine two companies operating identical factories:

- Company A has borrowed ₹300 crore.
- Company B has borrowed ₹50 crore.

Their operating businesses might generate exactly the same EBIT, but their PAT will differ because of interest expenses.

For evaluating the efficiency of the underlying business, we want to remove this financing difference.

That's why we use NOPAT.

## What is NOPAT Margin?

NOPAT Margin measures how much after-tax operating profit the company generates from every ₹100 of revenue.

\\[ NOPAT\ Margin=\frac{NOPAT}{Revenue}\times100 \\]

Using the example:

\\[ =\frac{112.5}{1000}\times100=11.25\\% \\]

Interpretation:

For every ₹100 of revenue, the business generates ₹11.25 of after-tax operating profit.

### How does this help identify the J-Curve?

Suppose a company expands its factory.

| Stage                | Revenue | NOPAT | NOPAT Margin |
| -------------------- | ------- | ----- | ------------ |
| Before expansion     | 1,000   | 120   | 12%          |
| Construction/ramp-up | 1,100   | 110   | 10%          |
| Initial utilization  | 1,300   | 143   | 11%          |
| Better utilization   | 1,600   | 192   | 12%          |
| Mature utilization   | 2,000   | 260   | 13%          |

Notice what happens:

- During the investment phase, NOPAT Margin declines.
- During ramp-up, it starts recovering.
- As utilization improves, operating leverage starts contributing.
- Eventually, the business generates more operating profit from every rupee of revenue.

This is one of the signals you want to identify.

My recommendation: Track NOPAT Margin alongside EBITDA Margin. EBITDA Margin tells you about operating profitability before depreciation; NOPAT Margin incorporates depreciation and tax, making it more useful for assessing returns on invested capital.

# 3. Total Capital Employed vs Total Invested Capital

This is an important distinction because the denominator determines whether your return calculation is meaningful.

Think of capital as the money required to operate and finance the business.

There are two related ways to look at it.

## A. Total Capital Employed (TCE)

Your spreadsheet calculates:

\\[ TCE=Equity+Reserves+Borrowings+Lease\ Liabilities \\]

In simple terms:

- Equity Capital: Money contributed by shareholders.
- Reserves: Profits retained in the business over the years.
- Borrowings: Money borrowed from banks and other lenders.
- Lease Liabilities: Capital-like obligations arising from leased assets.

This measures the capital supplied by shareholders and lenders to finance the business.

For example:

| Source                 | Amount |
| ---------------------- | ------ |
| Equity capital         | 100    |
| Reserves               | 400    |
| Borrowings             | 300    |
| Lease liabilities      | 50     |
| Total Capital Employed | 850    |

Think of TCE as the financing side of the business.

## B. Total Invested Capital (TIC)

Your spreadsheet calculates:

\\[ TIC=Equity+Reserves+Borrowings -Cash-Investments \\]

This is trying to measure the capital actually tied up in the business, excluding excess cash and non-operating investments.

Using the same example:

| Particulars            | Amount |
| ---------------------- | ------ |
| Equity + Reserves      | 500    |
| Borrowings             | 300    |
| Cash                   | (100)  |
| Investments            | (50)   |
| Total Invested Capital | 650    |

Why subtract cash?

Suppose a company has ₹300 crore of borrowings but also ₹250 crore sitting idle in its bank account.

It would be misleading to assume that the entire ₹300 crore of borrowing is being used to generate operating profits.

We therefore subtract cash to arrive at net capital invested.

### The important distinction

| Metric                     | What it tells you                                                   |
| -------------------------- | ------------------------------------------------------------------- |
| TCE                        | How much capital has been provided by shareholders and lenders      |
| TIC                        | How much net capital is considered invested in the business         |
| Operating Capital Employed | How much capital is tied up in operating assets and working capital |

These are three different perspectives.

## One important improvement to your spreadsheet

Your TCE formula includes lease liabilities, whereas your TIC formula excludes them.

This means your two capital figures are not perfectly comparable.

For a consistent ROIC calculation, I would consider including lease liabilities in invested capital, if lease liabilities are material and the operating profit is treated consistently.

Also, cash should ideally be divided into:

- Cash required for normal operations.
- Excess cash that is genuinely non-operating.

Subtracting all cash can overstate ROIC if a substantial portion is required to run the business.

Similarly, investments should only be deducted if they are non-operating investments.

My preference: Use operating invested capital as the primary denominator for evaluating the operating J-Curve. Keep the financing-based capital calculation as a cross-check.

# 4. ROCE vs ROIC

These are probably the two most important traditional ratios in your model.

Both measure how efficiently a company uses capital to generate profits.

But they measure slightly different things.

## A. ROCE — Return on Capital Employed

Your formula:

\\[ ROCE=\frac{EBIT}{Average\ Capital\ Employed} \\]

ROCE tells you how much operating profit the company generates for every ₹100 of capital employed.

Example:

- EBIT = ₹150 crore
- Opening capital employed = ₹750 crore
- Closing capital employed = ₹850 crore
- Average capital employed = ₹800 crore

\\[ ROCE=\frac{150}{800}=18.75\\% \\]

The company generates ₹18.75 of EBIT for every ₹100 of average capital employed.

## B. ROIC — Return on Invested Capital

Your formula:

\\[ ROIC=\frac{NOPAT}{Average\ Invested\ Capital} \\]

Suppose:

- NOPAT = ₹112.5 crore
- Average invested capital = ₹650 crore

\\[ ROIC=\frac{112.5}{650}=17.31\\% \\]

The company generates ₹17.31 of after-tax operating profit for every ₹100 of average invested capital.

## What's the actual difference?

| Dimension            | ROCE                         | ROIC                      |
| -------------------- | ---------------------------- | ------------------------- |
| Numerator            | EBIT                         | NOPAT                     |
| Tax consideration    | Before tax                   | After tax                 |
| Denominator          | Capital employed             | Invested capital          |
| Primary purpose      | Operating capital efficiency | After-tax economic return |
| Comparison with WACC | Less direct                  | More appropriate          |

### Why is ROIC particularly important?

Because it can be compared with WACC (Weighted Average Cost of Capital).

WACC is the average return expected by the providers of capital, considering the cost of equity and debt.

For example:

| Metric      | Value |
| ----------- | ----- |
| ROIC        | 18%   |
| WACC        | 12%   |
| ROIC - WACC | +6%   |

This means the business generates a return six percentage points above its estimated cost of capital.

That is generally a sign of value creation.

Now consider:

| Metric      | Value |
| ----------- | ----- |
| ROIC        | 8%    |
| WACC        | 12%   |
| ROIC - WACC | -4%   |

The business is generating less than its cost of capital.

It may be growing revenue and profits, but it is not necessarily creating economic value.

### How does this relate to the J-Curve?

During expansion, invested capital increases immediately.

But NOPAT takes time to catch up.

Consequently:

- ROIC initially declines.
- The new capacity starts generating revenue.
- NOPAT begins growing faster.
- ROIC starts recovering.
- Eventually ROIC may exceed its pre-expansion level.

This recovery is what you want to identify.

How invested capital and NOPAT interact

# ₹500 Cr

Additional invested capital

# ₹75 Cr

Additional annual NOPAT

\\[ Incremental\ Return=\frac{75}{500}=15\\% \\]

Illustrative return generated by the additional investment.

One important nuance: ROIC can decline during a growth investment phase without implying that the investment is bad. What matters is whether the new capital eventually earns an attractive return.

# 5. Understanding the incremental analysis rows

This is where your spreadsheet becomes particularly interesting.

Traditional financial ratios tell you how efficiently the company has used capital historically.

Incremental analysis tells you:

How efficiently is the company using the additional capital it is investing today?

This is a much more forward-looking question.

Let's use a simple example.

| Metric           | FY25  | FY26  |
| ---------------- | ----- | ----- |
| Revenue          | 1,000 | 1,300 |
| EBITDA           | 150   | 208   |
| EBIT             | 100   | 143   |
| NOPAT            | 75    | 107   |
| Invested Capital | 600   | 800   |

The incremental changes are:

| Metric           | Increment |
| ---------------- | --------- |
| Revenue          | +300      |
| EBITDA           | +58       |
| EBIT             | +43       |
| NOPAT            | +32       |
| Invested Capital | +200      |

Now let's understand each incremental ratio.

## A. Incremental Revenue

\\[ \Delta Revenue=Revenue_t-Revenue\_{t-1} \\]

This measures how much additional revenue the company generated compared with the previous year.

In our example:

\\[ 1300-1000=₹300Cr \\]

It is useful for understanding the absolute growth generated by the business.

But it doesn't tell us whether the growth was capital efficient.

## B. Incremental EBITDA

\\[ \Delta EBITDA=EBITDA_t-EBITDA\_{t-1} \\]

\\[ =208-150=₹58Cr \\]

This tells us how much additional operating profit was generated before depreciation, interest and tax.

## C. Incremental EBITDA Margin

\\[ \frac{\Delta EBITDA}{\Delta Revenue} \\]

\\[ =\frac{58}{300}=19.33\\% \\]

This is a particularly useful ratio.

It tells you that every additional ₹100 of revenue generated approximately ₹19.33 of additional EBITDA.

Compare this with the existing EBITDA Margin.

If the existing EBITDA Margin is 15%, but incremental EBITDA Margin is 19.33%, the business is demonstrating positive incremental operating leverage.

That is a good sign.

If incremental EBITDA Margin is only 8%, despite an existing EBITDA Margin of 15%, you should investigate why incremental business is less profitable.

## D. Incremental EBIT and Incremental NOPAT

These follow the same principle.

- Incremental EBIT = Additional operating profit after depreciation.
- Incremental NOPAT = Additional after-tax operating profit.

Incremental NOPAT is particularly important because it is the additional operating profit available to all capital providers after tax.

## E. Incremental capital employed and incremental invested capital

These measure the additional capital required to support business growth.

\\[ \Delta Capital=Capital_t-Capital\_{t-1} \\]

In our example:

\\[ 800-600=₹200Cr \\]

The company invested an additional ₹200 crore to generate ₹300 crore of additional revenue.

This leads to the most interesting ratios in your spreadsheet.

# 6. The five ratios you specifically want to focus on

I agree with your prioritization. These five ratios together provide a good picture of capital deployment, asset productivity, profitability and the investment cycle.

Let's examine them in detail.

## 6.1 Incremental Revenue / Incremental Invested Capital

\\[ \frac{\Delta Revenue}{\Delta Invested\ Capital} \\]

Using our example:

\\[ =\frac{300}{200}=1.5x \\]

Interpretation:

For every ₹1 of additional invested capital, the company generated ₹1.50 of additional annual revenue.

This is essentially an incremental capital productivity ratio.

### Why is this useful?

Imagine two companies:

| Metric                      | Company A | Company B |
| --------------------------- | --------- | --------- |
| Additional revenue          | 300       | 300       |
| Additional invested capital | 200       | 400       |
| Ratio                       | 1.50x     | 0.75x     |

Both companies generated ₹300 crore of additional revenue.

But Company A needed only half the additional capital.

Company A is demonstrating better capital efficiency.

### How does it help identify the J-Curve?

During the construction phase:

- Invested capital increases.
- Revenue has not yet started increasing significantly.
- This ratio may fall sharply.

During ramp-up:

- Revenue starts growing.
- Existing capacity gets utilized.
- The ratio starts recovering.

During maturity:

- The additional capacity generates substantial revenue.
- Capital productivity improves.

What you want to see

A recovery in this ratio after a period of heavy investment.

Important limitation: This ratio is not a profitability ratio. Revenue of ₹1.50 for every ₹1 invested does not tell you whether the investment earns an attractive return. You must combine it with incremental NOPAT / incremental invested capital.

Also, annual revenue and year-end capital changes are not perfectly time-aligned. A project commissioned halfway through the year may generate only six months of revenue against a full year-end capital addition.

## 6.2 Incremental NOPAT / Incremental Invested Capital

This is arguably the most important incremental ratio in your model.

\\[ \frac{\Delta NOPAT}{\Delta Invested\ Capital} \\]

Using our example:

\\[ =\frac{32}{200}=16\\% \\]

Interpretation:

The additional ₹200 crore of invested capital generated ₹32 crore of additional annual after-tax operating profit.

That's a 16% incremental return.

### Why is this more important than incremental ROIC?

Because traditional ROIC measures returns on the entire existing capital base.

Incremental ROIC measures returns on the additional capital deployed.

Consider:

| Metric           | FY25  | FY26  |
| ---------------- | ----- | ----- |
| Existing ROIC    | 12.5% | 13.4% |
| Incremental ROIC | —     | 16%   |

The company is generating a higher return on new capital than on its existing capital.

This suggests that new investments are potentially improving the overall economics of the business.

Now consider the opposite:

| Metric           | FY25 | FY26 |
| ---------------- | ---- | ---- |
| Existing ROIC    | 18%  | 15%  |
| Incremental ROIC | —    | 8%   |

This is a warning sign.

The company is earning only 8% on additional capital despite having an existing business earning 18%.

If WACC is 12%, the new investment may be destroying value.

### How does it help identify the J-Curve?

This is the ratio I would pay the most attention to when evaluating whether the investment cycle is delivering its intended returns.

The expected sequence is:

1. Heavy investment takes place.
2. Incremental ROIC is initially weak or negative.
3. New capacity becomes operational.
4. Revenue and operating profit start increasing.
5. Incremental ROIC improves.
6. Incremental ROIC eventually exceeds WACC.

However, one caution: a single year's incremental ROIC can be distorted by working capital movements, acquisitions, asset sales, exceptional items and timing differences.

I would evaluate it over a rolling two- or three-year period as well.

## 6.3 CWIP / Total Invested Capital

CWIP means Capital Work in Progress.

It represents money spent on assets that are still being constructed or are not yet ready for their intended use.

Your formula:

\\[ \frac{CWIP}{Total\ Invested\ Capital} \\]

Suppose:

- CWIP = ₹200 crore.
- Total invested capital = ₹1,000 crore.

\\[ =\frac{200}{1000}=20\\% \\]

This means 20% of the company's measured invested capital is currently sitting in projects under construction.

### Why is this important?

CWIP is a leading indicator of potential future capacity.

Think of it this way:

| Financial metric | What it tells you                                          |
| ---------------- | ---------------------------------------------------------- |
| Revenue          | What the company is generating today                       |
| EBITDA           | What operating profits it is generating today              |
| ROIC             | How efficiently existing capital is working                |
| CWIP             | How much capital is being deployed towards future capacity |

CWIP can help you identify where the company is in its investment cycle.

For example:

Illustrative investment-cycle progression

1. High CWIP / rising invested capital

   Significant construction and investment activity. Current returns may be under pressure.
2. CWIP starts declining

   Projects are commissioned and transferred into fixed assets.
3. Fixed assets and depreciation increase

   The new capacity becomes operational, and depreciation begins affecting EBIT.
4. Revenue and utilization increase

   The newly commissioned capacity begins contributing to sales.
5. Incremental NOPAT and ROIC improve

   The investment starts producing financial returns.

### What should you look for?

A high CWIP ratio is not automatically positive.

It becomes interesting when you can establish:

- What projects are being constructed?
- When will they be commissioned?
- What additional capacity will they provide?
- What is the expected utilization ramp-up?
- What additional revenue and profitability can they generate?

A company with 25% CWIP but repeatedly delayed projects may be in a much worse position than one with 10% CWIP and projects nearing commissioning.

My recommendation: Track absolute CWIP, CWIP / Invested Capital, and CWIP converted into fixed assets. Also examine capital expenditure commitments and commissioning timelines.

## 6.4 Revenue / Average Invested Capital

This is commonly called Invested Capital Turnover.

\\[ \frac{Revenue}{Average\ Invested\ Capital} \\]

Suppose:

- Revenue = ₹1,300 crore.
- Average invested capital = ₹700 crore.

\\[ =\frac{1300}{700}=1.86x \\]

Interpretation:

For every ₹1 of average invested capital, the company generates ₹1.86 of annual revenue.

This measures how productively the company is using its capital to generate sales.

### Why is this useful?

Consider two manufacturers:

| Metric                   | Company A | Company B |
| ------------------------ | --------- | --------- |
| Revenue                  | 1,000     | 1,000     |
| Average invested capital | 500       | 1,000     |
| Capital turnover         | 2.0x      | 1.0x      |

Both generate identical revenue.

But Company A requires only half the capital.

Company A has better capital productivity.

### How does it help identify the J-Curve?

During expansion:

- The company invests in new factories and machinery.
- Invested capital increases.
- Revenue may not immediately increase.
- Capital turnover declines.

Once the new factory starts operating:

- Revenue begins increasing.
- Capacity utilization improves.
- Capital turnover starts recovering.

This ratio helps you understand whether the business is extracting more revenue from its capital base.

### A particularly useful relationship

ROIC can be broken down into two components:

\\[ ROIC=NOPAT\ Margin\times Invested\ Capital\ Turnover \\]

For example:

| Metric                    | Value |
| ------------------------- | ----- |
| NOPAT Margin              | 10%   |
| Invested Capital Turnover | 2.0x  |
| ROIC                      | 20%   |

This is a powerful relationship.

A company can improve ROIC in two ways:

1. Improve profitability: Generate more NOPAT from each rupee of revenue.
2. Improve capital productivity: Generate more revenue from each rupee of invested capital.

You should track both separately.

## 6.5 EBITDA / Revenue

This is the EBITDA Margin.

\\[ EBITDA\ Margin=\frac{EBITDA}{Revenue} \\]

Suppose:

- Revenue = ₹1,000 crore.
- EBITDA = ₹200 crore.

EBITDA Margin = 20%.

Interpretation:

For every ₹100 of revenue, the company generates ₹20 of EBITDA.

### Why is this useful in J-Curve analysis?

Manufacturing companies generally have fixed costs:

- Factory rent.
- Salaries of permanent employees.
- Maintenance.
- Certain administrative expenses.
- Depreciation is excluded from EBITDA but reflects the capital intensity of the business.

Suppose a factory is designed for annual production of 100,000 units.

The factory incurs substantial fixed costs even when producing only 30,000 units.

At 30% utilization, the fixed costs are spread over fewer units.

At 80% utilization, those same fixed costs are spread over more units.

Consequently, profitability per unit can improve.

This is called operating leverage.

### Example

| Metric        | Low utilization | High utilization |
| ------------- | --------------- | ---------------- |
| Revenue       | 500             | 1,000            |
| EBITDA        | 50              | 180              |
| EBITDA Margin | 10%             | 18%              |

Revenue doubled, but EBITDA increased 3.6 times.

This is a strong illustration of operating leverage.

What you want to see

An improving EBITDA Margin alongside improving capacity utilization and incremental revenue.

However, EBITDA Margin alone cannot establish a successful J-Curve. A company can report improving margins while investing excessively in new capacity. You need to evaluate capital productivity as well.

# 7. How to combine these five ratios to identify the J-Curve

This is where I would move away from looking at individual ratios and start looking at them together.

Each ratio tells you something different.

| Ratio                                              | Question it answers                                    | What you want to observe                   |
| -------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------ |
| Incremental Revenue / Incremental Invested Capital | Is additional capital generating sales efficiently?    | Recovery/improvement                       |
| Incremental NOPAT / Incremental Invested Capital   | Is additional capital generating attractive returns?   | Improvement above WACC                     |
| CWIP / Total Invested Capital                      | How much capital is waiting to become productive?      | Projects progressing towards commissioning |
| Revenue / Average Invested Capital                 | How productively is the total capital base being used? | Recovery after expansion                   |
| EBITDA / Revenue                                   | Is operating profitability improving?                  | Improving margins as utilization rises     |

I would interpret these ratios as a sequence rather than five independent indicators.

## The complete J-Curve interpretation framework

## Phase 1: Heavy investment

Capital deployment

- CWIP / Invested Capital increases.
- Invested Capital increases.
- Revenue growth may remain modest.
- Revenue / Invested Capital declines.
- ROIC may decline.

## Phase 2: Commissioning and ramp-up

Early recovery

- CWIP starts converting into fixed assets.
- Depreciation increases.
- Revenue growth accelerates.
- Incremental Revenue / Invested Capital improves.
- EBITDA Margin starts recovering.

## Phase 3: Operating leverage

Profit conversion

- Capacity utilization improves.
- Incremental EBITDA Margin improves.
- NOPAT grows faster.
- Incremental NOPAT / Invested Capital improves.
- Revenue / Invested Capital recovers.

## Phase 4: Mature returns

Value creation

- ROIC recovers.
- ROIC exceeds WACC.
- Incremental returns remain attractive.
- Cash generation improves.
- The new investment starts creating economic value.

One important distinction: the ratios do not necessarily improve in this exact order or at the same time. For example, EBITDA Margin may improve before capital turnover recovers.

The framework is a way to understand the economic progression, not a rigid forecasting model.

# 8. Applying this thinking to your two spreadsheets

Now let's connect the concepts to the actual models you prepared.

I noticed that your sheets have two useful analytical sections:

1. Incremental P&L Analysis.
2. Incremental Balance Sheet Analysis.

This is a good structure because it allows you to connect additional capital deployed with the additional operating profit generated.

## A. Your Sansera model

Your Sansera sheet contains:

- Revenue and incremental revenue.
- EBITDA, EBIT, PAT and NOPAT.
- Incremental EBITDA, EBIT, PAT and NOPAT.
- Capital employed and invested capital.
- CWIP.
- ROCE and ROIC.
- Incremental capital productivity ratios.

I particularly like that you have separated capital employed, invested capital and operating capital employed.

This allows you to investigate whether the company's growth is being driven by:

- Better utilization of existing assets.
- Additional capital investment.
- Improved margins.
- Better working capital efficiency.

For Sansera, I would pay particular attention to the relationship between incremental revenue, incremental invested capital and incremental NOPAT.

A manufacturer can grow revenue because of a significant increase in fixed assets and working capital. The key is whether the additional investment generates sufficient after-tax operating profit.

## B. Your Anthem model

Your Anthem model uses essentially the same structure.

There is one additional consideration: your balance sheet contains substantial changes in working capital across certain years.

For example, your spreadsheet shows:

- FY24 inventory: ₹211.35 crore.
- FY25 inventory: ₹340.43 crore.
- FY26 inventory: ₹124.52 crore.
- Latest inventory: ₹188.59 crore.

Receivables also fluctuate considerably.

These changes can materially affect invested capital and operating capital employed.

Therefore, if incremental ROIC changes substantially in a particular year, investigate whether the change came from:

1. Actual improvement in operating profitability.
2. Reduction in working capital.
3. Capital expenditure.
4. Asset disposals or other balance-sheet movements.

Otherwise, you might incorrectly conclude that the underlying business economics have improved.

# 9. Important improvements I would make to your Excel models

I noticed a few things worth correcting or considering before relying heavily on the results.

### 1. Be consistent with lease liabilities

Your Total Capital Employed includes lease liabilities, but Total Invested Capital excludes them.

Consider including lease liabilities in invested capital if material, and use a consistent treatment of lease-related operating expenses and profits.

### 2. Separate operating and excess cash

Your current invested capital formula subtracts all cash.

A better economic calculation is:

\\[ IC=Equity+Debt+Lease\ Liabilities \\]

\\[ -Excess\ Cash-NonOperating\ Investments \\]

Cash required for normal operations should not automatically be excluded.

### 3. Improve the incremental ratio formulas

Your current formulas contain a special negative-value adjustment, for example:

`IF(AND(Revenue Change<0, Capital Change<0), -1*Revenue Change/Capital Change, ...)`

I would avoid this adjustment.

Instead:

- Display the raw incremental numerator.
- Display the raw incremental denominator.
- Calculate the ratio only when the capital increase is positive and meaningful.
- Show N/A when capital change is zero, negative or unusually small.

Why?

Suppose revenue declines by ₹100 crore and invested capital declines by ₹50 crore.

The mathematical ratio is positive 2x, but that does not mean the company has achieved 2x capital productivity. It may simply have contracted its operations.

Likewise, a very small denominator can produce an unusually high incremental return.

### 4. Be careful with the Latest column

This is particularly important.

Your P&L metrics are flows over a period, whereas balance sheet figures are snapshots at a particular date.

If Latest represents nine months of financial results, you cannot directly compare those numbers with a full financial year.

For meaningful incremental analysis, use comparable periods:

- FY25 versus FY26.
- 9M FY26 versus 9M FY27.
- Or TTM versus previous TTM.

Do not compare nine-month revenue growth against a full-year change in invested capital without making the periods comparable.

### 5. Use average invested capital consistently

Your ROIC formula correctly uses average invested capital.

However, your incremental ROIC uses the change in year-end invested capital.

These answer different questions:

- ROIC: Return on the average capital employed throughout the year.
- Incremental ROIC: Additional NOPAT generated relative to the change in capital between two balance-sheet dates.

For major capacity additions, I would also examine quarterly or half-yearly capital movements to understand timing.

### 6. Check the effective tax rate

You calculate NOPAT using EBIT multiplied by one minus the effective tax rate.

That is a reasonable starting point.

However, actual tax expense divided by PBT can be distorted by exceptional items, deferred tax and unusual tax adjustments.

For a more normalized ROIC calculation, consider using a normalized operating tax rate rather than blindly applying the reported effective tax rate in every year.

# 10. My suggested J-Curve dashboard

If I were refining your spreadsheets, I would create a small dashboard with these metrics.

I would divide them into three groups.

A. Capital deployment

| KPI                        | Purpose                     |
| -------------------------- | --------------------------- |
| CWIP / Invested Capital    | Investment pipeline         |
| Capex / Revenue            | Investment intensity        |
| Change in Invested Capital | Additional capital deployed |
| Fixed Asset Growth         | Capacity expansion          |

B. Capital productivity

| KPI                                                | Purpose                        |
| -------------------------------------------------- | ------------------------------ |
| Revenue / Average Invested Capital                 | Sales productivity             |
| Incremental Revenue / Incremental Invested Capital | Incremental sales productivity |
| Operating Capital Employed / Revenue               | Operating capital intensity    |

C. Return generation

| KPI              | Purpose                           |
| ---------------- | --------------------------------- |
| EBITDA / Revenue | Operating profitability           |
| NOPAT Margin     | After-tax operating profitability |
| ROIC             | Overall capital returns           |
| Incremental ROIC | Returns on additional capital     |
| ROIC - WACC      | Economic value creation           |

I would also add two things that aren't explicitly captured in your current five priority ratios:

1\. Capacity utilization

This is particularly important for manufacturing companies. It helps explain why revenue and profitability are improving or deteriorating.

2\. Operating cash flow / NOPAT

Accounting profits should eventually translate into cash. If NOPAT improves but operating cash flow consistently fails to follow, investigate receivables, inventory and other working capital requirements.

# 11. The most important mental model to remember

I want you to remember these three questions whenever you analyse a company undergoing expansion.

### 1. How much are they investing?

CWIP, Capex, Change in Invested Capital.

Understand the size and timing of the investment.

### 2. How efficiently is the investment being utilized?

Revenue / Invested Capital, Incremental Revenue / Incremental Invested Capital, Capacity Utilization.

Understand whether the new assets are becoming productive.

### 3. What returns is the investment generating?

EBITDA Margin, NOPAT Margin, Incremental ROIC, ROIC - WACC.

Understand whether the additional business is economically attractive.

The ultimate objective is to connect these three questions.

Investment → Utilization → Revenue → Operating Profit → NOPAT → ROIC

That is the economic story behind a J-Curve.

## My final recommendation for your learning process

I would not try to interpret all 20–25 financial metrics simultaneously.

Start with these five, in this order:

1. CWIP / Invested Capital: Is the company currently investing heavily?
2. Revenue / Average Invested Capital: Is its existing capital becoming more productive?
3. Incremental Revenue / Incremental Invested Capital: Is new investment generating sales efficiently?
4. EBITDA / Revenue: Is incremental growth translating into operating profitability?
5. Incremental NOPAT / Incremental Invested Capital: Is the new investment generating attractive after-tax returns?

Then use ROIC versus WACC to determine whether the business is creating economic value.

One final caution: a J-Curve is not automatically a good investment opportunity. You also need to establish that the expected recovery is realistic, that the company has sufficient financial resources to complete its projects, and that demand will absorb the additional capacity.

The distinction I would keep in mind is this: identifying a J-Curve tells you where the business might be in its investment cycle; evaluating incremental ROIC tells you whether that investment cycle is likely to create shareholder value.

My suggested next step would be to take Sansera and Anthem separately and work through their actual historical numbers, ratio by ratio, so that you can see how these concepts translate into real company financials rather than relying only on hypothetical examples.