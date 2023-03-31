# Power simulations for the project: "Infants and dogs' perception of causality and animacy: a systematic comparative investigation"

| Study | Response variable           | error structure | test condition 1                               | test condition 2 | control condition                         | subject.sd | residual.sd | N  | power | design          | model                                                     |
|-------|-----------------------------|-----------------|------------------------------------------------|------------------|-------------------------------------------|------------|-------------|----|-------|-----------------|-----------------------------------------------------------|
| 1     | pupil size                  | gaussian        | gap: 500                                       | lag: 500         | launch: 0                                 | 500        | 350         | 24 | 85.5% | within          | lmer(resp~condition + sex + z.order + (1\|subject))       |
| 2     | pupil size                  | gaussian        | incongruent: 500                               |                  | congruent: 0                              | 500        | 350         | 24 | 99.9% | within          | lmer(resp~condition + sex + z.order + (1\|subject))       |
| 3     | pupil size                  | gaussian        | incongruent: 500 / 0  (launch / control group) |                  | congruent: 0 / 0 (launch / control group) | 250        | 250         | 40 | 85.2% | within/between  | lmer(resp~group*condition + sex + z.order + (1\|subject)) |
| 4     | proportion interaction time | beta            | ambiguous: 0.7                                 |                  | hand control: 0.5                         |            |             | 40 | 97.5% | between         | glm(resp~condition + sex, family=beta)                    |
| 5     | pupil size                  | gaussian        | gap: 500 / 0 (hand / train group)              |                  | contact: 0 / 0 (hand / train group)       | 250        | 250         | 24 | 85.2% | within/between  | lmer(resp~group*condition + sex + z.order + (1\|subject)) |
| 6     | pupil size                  | gaussian        | inefficient: 500 / 0 (obstacle / clear group)  |                  | efficient: 0 / 0 (obstacle / clear group) | 250        | 250         | 40 | 85.2% | within/between  | lmer(resp~group*condition + sex + z.order + (1\|subject)) |

## Structure 

```
.
├── Study 1           <-- Power analysis for study 1 of baseline corrected pupil size data using a Linear Mixed Model (LMM).
├── Study 2           <-- Power analysis for study 2 of baseline corrected pupil size data using a Linear Mixed Model (LMM).
├── Study 3/5/6       <-- Power analysis for study 3, 5, and 6 of baseline corrected pupil size data using a Linear Mixed Model (LMM).
├── Study 4           <-- Power analysis for study 4 of proportion interaction time data using a GLM (beta error structure).
└── functions         <-- Function for beta GL(M)M. Function kindly provided by Roger Mundry. 

```