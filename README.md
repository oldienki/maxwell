# Maxwell: The Gatekeeper

**High-performance and lightweight** L7 smart firewall / security gateway for modern **Home** OpenWrt routers

Built in **Rust** on top of **eBPF**, **nDPI**, **nftables**, and **tc (CAKE)** for `aarch64` (Cortex-A53) devices running OpenWrt 24.10+ (Kernel 6.6).

### Key Highlights
* **Fast-Path Friendly DPI:** Inspects only the first few packets of a flow via eBPF RingBuf + userspace `libndpi`, keeping unthrottled traffic in hardware offload (HNAT) at 2.5 Gbps line rate.
* **Per-Flow Shaping & Schedules:** Enforces time-based app blocking and anti-bufferbloat throttling (`act_ctinfo` + `CAKE`) with instant `conntrack` state eviction when schedules trigger.
* **BTF-Free Stock Kernel Support:** Powered by `aya-rs` without requiring `CONFIG_DEBUG_INFO_BTF` or custom kernel rebuilds.
* **AI-Ready Observability (MCP):** Exposes local EWMA/Z-score anomaly detection and structured telemetry via an outbound-tunneled Model Context Protocol (MCP) interface.

