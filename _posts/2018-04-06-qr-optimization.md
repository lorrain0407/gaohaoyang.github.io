---
layout: post
title:  "QR Optimization"
date:   2018-04-06 9:33:45
categories: QR_Code
tags: C++ QR_Code
---

* content
{:toc}

A project about QR Optimization for easily generating a 3D QR Code later.

## Our Goal

Increase the overall contrast by optimizing the distribution of black modules without violating readability.

## Our Intuition

An isolated module gives higher contrast than one with black neighborhoods.

## Compile

Compile this project using the standard cmake routine:

```
mkdir build
cd build
cmake ..
make
```

## Run

From within the `build` directory just issue:

```
./example_bin
```

## Algorithm

```
1 Find all connected black non-functional components $CC$
2 Calculate the visibilit $V_{CC_i}$ of each $CC_i\inCC$ and push them into $PQ$ in an ascending order;
3 While ($PQ$ not empty) {
	1.Popup $CC$ from $PQ$;
	2.If $CC$ can be dispersed, 
		  flip one module;
		  Continue;
	  Else
		  goto step3.1;
	4 Find all connected black non-functional components $$CC$$
	5 Calculate the visibility $V_{CC_I}$ of each $CC_i\inCC$ and push them into $PQ$;
  }
4 Return the current QR

```

You should clearly understand the coding ruls of QR Code first, otherwise, you can not know which $$CC$$ can be dispersed.

## Results

You can see some results in results directory.  