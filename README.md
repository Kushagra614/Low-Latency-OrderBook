# Low-Latency Order Book Engine

A high-performance, feed-driven limit order book engine built in C++20. This engine processes a synthetic stream of order events (New, Cancel, Modify, Market) using a lock-free ring buffer and maintains a cache-aware bid/ask book with price-time priority matching.

## Supported Order Types
* **Limit Order (GTC):** Good-Till-Cancel limit order (rests in the book).
* **Market Order:** Price-independent execution, matches top of book immediately, cancels remainder.
* **IOC (Immediate-Or-Cancel / FAK):** Fills what is possible immediately at or better than limit price, cancels remainder.
* **FOK (Fill-Or-Kill):** All-or-nothing execution at or better than limit price, cancels entire order if not fully fillable.
* **Cancel Order:** Immediate removal of a resting order by its ID.
* **Modify Order:** Changes price or quantity, enforcing time-priority rules.

