# IntervalTree
[![Linux Build Status](https://travis-ci.org/IvanPinezhaninov/IntervalTree.svg?branch=master)](https://travis-ci.org/IvanPinezhaninov/intervaltree)

## Overview

A red-black self-balancing interval tree C++11 implementation

## Usage

```c++
#include <iostream>
#include "intervaltree.hpp"

int main()
{
    // Create an interval tree
    Intervals::IntervalTree<int> intervalTree;

    // Insert intervals to the tree
    intervalTree.insert({ 20, 30 });
    intervalTree.insert({ 40, 60 });
    intervalTree.insert({ 70, 90 });
    intervalTree.insert({ 60, 70 });
    intervalTree.insert({ 40, 90 });
    intervalTree.insert({ 80, 90 });

    // Find intervals
    auto overlapingIntervals = intervalTree.findOverlappingIntervals({ 50, 80 });
    auto innerIntervals = intervalTree.findInnerIntervals({ 50, 80 });
    auto outerIntervals = intervalTree.findOuterIntervals({ 50, 80 });

    // Print all intervals
    std::cout << "All intervals:" << std::endl;
    for (auto interval : intervalTree.intervals()) {
        std::cout << interval << std::endl;
    }
    std::cout << std::endl;

    // Print overlapping intervals
    std::cout << "Overlapping intervals:" << std::endl;
    for (auto interval : overlapingIntervals) {
        std::cout << interval << std::endl;
    }
    std::cout << std::endl;

    // Print inner intervals
    std::cout << "Inner intervals:" << std::endl;
    for (auto interval : innerIntervals) {
        std::cout << interval << std::endl;
    }
    std::cout << std::endl;

    // Print outer intervals
    std::cout << "Outer intervals:" << std::endl;
    for (auto interval : outerIntervals) {
        std::cout << interval << std::endl;
    }

    return 0;
}
```
