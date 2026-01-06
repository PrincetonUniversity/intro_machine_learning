# Day 2 Solutions


#### Exercise 1

```python
np.mean(abs(results["truth"] - results["prediction"]))
```


#### Exercise 2

```python
k_values = [i for i in range(1,101)]    # a list containing values 1 through 100

scores_uniform = get_scores(X_train, X_test, Y_train, Y_test, k_values, weight_function = "distance", distance_metric = "l2")
scores_distance = get_scores(X_train, X_test, Y_train, Y_test, k_values, weight_function = "distance", distance_metric = "l1")

# plot results
sns.set(style='whitegrid',font_scale=1.3, rc={'figure.figsize':(5,5)})
p = sns.lineplot(x=k_values, y=scores_uniform, color='darkblue')
sns.lineplot(x=k_values, y=scores_distance, color='darkred')
p.set(xlabel="k neighbors", ylabel="score", title="red:l1, blue:l2")

print("Best uniform score: ", max(scores_uniform))
print("Best distance score: ", max(scores_distance))
```
