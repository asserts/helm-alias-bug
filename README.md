# Helm Alias Bug Test Case

## Reference

Bug similar to issue https://github.com/helm/helm/issues/7729

## Running

### Sad Path

`helm install parent charts/sad-parent`

This will show only a pod called `child`. It will not respect the aliases.

Note that the `version` for the dependent child chart is commented out in `sad-parent/Chart.yaml`


### Happy Path

`helm install parent charts/happy-parent`

This will show 2 pods, one called `childone` and another called `childtwo`. 

Note that the `version` is set in `happy-parent/Chart.yaml`

## Cleanup

`helm delete parent`
