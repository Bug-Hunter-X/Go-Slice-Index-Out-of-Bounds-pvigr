# Go Slice Index Out of Bounds

This repository demonstrates a common error in Go: accessing a slice index that is out of bounds.  The provided `bug.go` file contains a function with a loop that incorrectly iterates over a slice, leading to a runtime panic. The corrected version is in `bugSolution.go`.

## How to Reproduce

1. Clone this repository.
2. Run `go run bug.go`.
3. Observe the runtime panic.
4. Run `go run bugSolution.go` to see the correct solution.

## Root Cause

The error stems from the loop condition `i <= len(a)`. In Go, slices are zero-indexed, meaning the valid indices range from `0` to `len(a) - 1`.  When `i` reaches `len(a)`, the attempt to access `a[i]` results in an out-of-bounds access and a panic.

## Solution

The solution is to change the loop condition to `i < len(a)`, ensuring that `i` always remains within the valid index range of the slice.