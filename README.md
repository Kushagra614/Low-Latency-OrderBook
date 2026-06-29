# Low-Latency Order Book Engine

A high-performance, feed-driven limit order book engine built in C++20. This engine processes a synthetic stream of order events (New, Cancel, Modify, Market) using a lock-free ring buffer and maintains a cache-aware bid/ask book with price-time priority matching.
