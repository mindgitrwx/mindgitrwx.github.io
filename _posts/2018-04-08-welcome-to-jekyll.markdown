---
layout: post
title:  "first post"
j
categories: jekyll update
---

java markup test

{% highlight java %}

    public boolean isSatisfied(IterationHistory iterationHistory) {
        if (iterationHistory.getIterationCount() <= period)
            return false;

        for (int i = 0, j = iterationHistory.getIterationCount(); i < period; i++) {
            double variation = iterationHistory.getIterationInfo(j - i).getClusterSetInfo()
                            .getPointDistanceFromClusterVariance();
            variation -= iterationHistory.getIterationInfo(j - i - 1).getClusterSetInfo()
                            .getPointDistanceFromClusterVariance();
            variation /= iterationHistory.getIterationInfo(j - i - 1).getClusterSetInfo()
                            .getPointDistanceFromClusterVariance();

            if (!varianceVariationCondition.apply(variation))
                return false;
        }

        return true;
    }

{% endhighlight %}

