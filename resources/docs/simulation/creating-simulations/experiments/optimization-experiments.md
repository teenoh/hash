---
description: How to use HASH to optimize your simulation's parameters
---

# Optimization Experiments

Often, when running an experiment, you don't necessarily want to see every simulation's outcomes, you want to find the best ones, the parameters that **optimize** a desired metric. With HASH's optimization engine, you can automatically generate simulations and find the set of parameters that will maximize or minimize a metric.

{% hint style="info" %}
Optimization experiments can only be run on [hCloud](../h.cloud.md)
{% endhint %}

## Creating Optimization Experiments

To create an optimization experiment, first create the metric that represents the value you want to optimize.

{% hint style="info" %}
[Read more on defining metrics](../views/analysis/metrics.md).
{% endhint %}

For example, in [Sugarscape](https://staging.hash.ai/@hash/sugarscape/stable), you might be interested in what parameters will optimize the average sugar of cells. In that case you can use the existing metric:

![Metric defined in Sugarscape](../../.gitbook/assets/image%20%2858%29.png)

Now use the experiment wizard to create a new experiment and fill in the options:

* Select `optimization` as the type.
* Use the metric name you previously defined as the metric.
* Decide whether to `maximize` or `minimize` the objective.
* Select the fields \([globals](../configuration/)\) that will be varied.

![](../../.gitbook/assets/image%20%2860%29%20%281%29.png)

You can save without running or save and run immediately in hCloud.

{% hint style="warning" %}
To run a simulation in hCloud, you must first set the [Behavior Keys](../behaviors/behavior-keys.md) of your simulations behaviors.
{% endhint %}

While the optimization experiment is running, individual runs will populate the experiment queue in the activity sidebar. Hover over a run to see the metrics value and the parameters for that particular run.

![In-progress optimization run](../../.gitbook/assets/image%20%2860%29.png)

When the optimization run completes, the best run - the run where the parameters maximized or minimized the metric - will be highlighted.

![](../../.gitbook/assets/image%20%2861%29.png)


