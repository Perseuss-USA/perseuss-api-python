# Perseuss Shipping Label API

The Perseuss Shipping Label API enables warehouses, 3PLs, and fulfillment systems to create real-time shipping labels, retrieve tracking numbers, and get accurate carrier rates — starting with **Better Trucks** as the first supported carrier.

Use this API to integrate label generation directly into your WMS, OMS, or shipping workflow.

---

## 🔑 Authentication

All API requests must include an authentication token in the request header:

| Header Name     | Value                | Required |
|-----------------|----------------------|---------|
| `X-API-Token`   | YOUR_API_KEY         | Yes     |

To request an API key, email:

📧 **tom@getperseuss.com**

> Requests without a valid API token will be rejected.

---

## 🚚 Generate Shipping Label

### **HTTP Request**
POST https://backend.perseuss.xyz/tms/generate_label/v1

### **Headers**

```http
Content-Type: application/json
X-API-Token: YOUR_API_KEY_HERE

```