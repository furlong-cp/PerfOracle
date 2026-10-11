# PerfOracle

A C++ performance engineering laboratory focused on understanding how data structures, memory layout, concurrency, and CPU behavior affect software performance.

## Overview

Performance optimization should be driven by measurements rather than intuition.

PerfOracle provides a collection of controlled experiments for comparing implementations, identifying bottlenecks, and documenting the trade-offs between throughput, latency, and resource usage.

## Core Experiments

* **Queue Implementations:** Compare mutex-protected queues with single-producer/single-consumer ring buffers.
* **Memory Layout:** Investigate contiguous versus pointer-heavy data structures.
* **Cache Locality:** Study access patterns and their effect on runtime.
* **False Sharing:** Explore cache-line contention between concurrent threads.
* **Memory Allocation:** Compare allocation strategies and reuse.
* **Batch Processing:** Measure the effects of processing multiple messages per operation.
* **Concurrency:** Examine atomic operations and memory-ordering trade-offs.

## Technical Stack

* Modern C++
* CMake
* Google Benchmark
* GoogleTest
* Linux `perf` and profiling tools
* AddressSanitizer and ThreadSanitizer where applicable

## Benchmarking Principles

Each experiment should document:

1. Hardware and operating-system configuration.
2. Compiler version and optimization flags.
3. Input size and workload characteristics.
4. Warm-up and repetition methodology.
5. Throughput and latency measurements.
6. Correctness tests and known limitations.

## Metrics

* Operations or messages per second
* Median and tail latency
* CPU utilization
* Cache misses and branch behavior where measurable
* Memory consumption
* Scaling with workload size and thread count

## Example Research Questions

* When does a ring buffer outperform a mutex-protected queue?
* How does memory layout affect traversal performance?
* What causes performance to deteriorate as the working set grows?
* Does batching improve throughput at the expense of individual-message latency?
* Which optimizations survive repeated measurements?

## Project Structure

Experiments will be organized into independent modules, each with its own benchmark implementation, results, and interpretation.

## Project Status

Under development. Benchmark tables will be added after experiments are implemented and repeated under documented conditions.

## Philosophy

Measure first. Optimize second. Validate always.
