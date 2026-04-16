# MUSI 2526: Audio Tech II - Project 2
The full development process, including the code for the training of both models is located in "index.ipynb" and
documented there. There is also an additional notebook, "eval.ipynb", which contains all 

Please place the ballroom dataset in a "data/" directory at this level. I have uploaded the
dataset with directories already properly formatted
[here](https://drive.google.com/file/d/1ugdeDSyl4hgoJLq04wlTGiBIqnBk2Ev_/view?usp=drive_link).

## Model Summary
### Baseline Model

- First deriviative of RMSE with trimmed negative values used as novelty
- 0.03 used as peak threshold in naive version
- Gradient ascent used to obtain ideal 0.03729 threshold in optimized version

### Improved Model

- Many additional features (spectral flux, zero-crossing rate, MFCC's 0-19) considered and evaluated individually
- Top three features (RMSE, spectral flux, MFCC 0) used in combined novelty function
- (Normalized) features simply added together in naive model
- Weighted sum used in optimized model; weights were optimized using experimentation, then multi-variate gradient ascent

### Extension Task

- Use autocorrelation on improved novelty function
- In the naive model pick the highest peak from beat histogram
- In optimized model prioritize more common tempo values in peak picking (closer to average)