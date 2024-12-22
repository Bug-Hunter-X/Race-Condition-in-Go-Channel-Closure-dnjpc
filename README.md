# Go Race Condition in Channel Closure

This repository demonstrates a subtle race condition that can occur in Go programs when closing channels. The issue arises when a `WaitGroup` is used to coordinate goroutines that send values to a channel, and the channel closure is handled in a separate goroutine.  Under certain conditions, the `wg.Wait()` call might finish before all goroutines have sent their data, leading to some values being lost.

The `bug.go` file contains the code with the race condition.  `bugSolution.go` provides a corrected version.  Read the comments within the files for detailed explanation.