#  gradual unfreezing design
## Code. 
This part's whole [source code](https://github.com/liketheflower/graph_classification_jak/blob/c36f2961613e7fc22195fc67dfc33cf139b8f32d/gin/jak_classification_random_split_GIN_GAE.py)

```python
_FREEZE_KEY = {'0': ['ginlayers.0','linears_prediction_classification.0'],
               '1': ['ginlayers.1','linears_prediction_classification.1'],
               '2': ['ginlayers.2','linears_prediction_classification.2'],
               '3': ['ginlayers.3','linears_prediction_classification.3'],
               '4': ['ginlayers.4','linears_prediction_classification.4'],
               }
```

The model is freezed by calling this function.
```python
def freeze_model_weights(model, layers='0'):
```

The frozen and unfrozen is controlled in the code shown here
```python
           if epoch == args.pretrain_epochs:
                # reinitialize the scheduler
                model = freeze_model_weights(model, layers='01234')
                optimizer = optim.Adam(filter(lambda p: p.requires_grad, model.parameters()), lr=args.lr)
                scheduler = optim.lr_scheduler.StepLR(optimizer, step_size=50, gamma=0.5)
            # stop frozen after the number of freeze_epochs
            if epoch == (args.pretrain_epochs+args.freeze_epochs):
                model = unfreeze_model_weights(model)
                optimizer = optim.Adam(model.parameters(), lr=args.lr/(2**(args.freeze_epochs/50.)))
                scheduler = optim.lr_scheduler.StepLR(optimizer, step_size=50, gamma=0.5)
```


