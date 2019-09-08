
# Credit risk

Calculated as an expected loss:

Expected loss = Exposure x Probability of default x Loss given default

Credit events

- Actions associated with bankruptcy or insolvency
- Rating agency downgrade
- Failure to pay
- Repudiation i.e. coupon not paid on time
- Restructuring i.e. terms of an obligation are altered so as to make the new terms less attractive to the debt holder. Could be a reduction in interest rate or change in level of seniority.

## Aproaches to modelling credit risk

**Structural** models represent a firm's assets and liabilities and define a mechanism for default.
Typically, default occurs when a random variable hits a barrier representing default.
The main example of a structural model is the *Merton* model.

**Reduced-form** models do not attempt a representation of the firm.
They are statistical models that use observed data, both macro and micro.
Market statistics are most often credit ratings.
Ratings agencies regularly review ratings.
Default is not tied to firm value but occurs according to some exogeneous hazard rate process.

**Intensity-based** models are a particular type of continuous time reduced-form model.
They typically models the jumps between states, usually credit ratings, using transition intensities.
A disadvantage of reduced-form models is that they sometimes lack the clarity of structural models.
