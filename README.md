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

### **Request Body Parameters**
```json
{
  "parcel": {
    "width": 5,
    "length": 3,
    "height": 5,
    "weight": 10.2,
    "uom_weight": "lb",
    "uom_distance": "in"
  },
  "origin": {
    "street1": "999 S Oyster Avenue",
    "city": "Bethpage",
    "state": "NY",
    "postal_code": "11714",
    "country": "US",
    "street2": "#111A",
    "name": "John Doe",
    "company": "JD Distribution",
    "phone": "123-345-5678",
    "email": "andrew@medusadistribution.com"
  },
  "destination": {
    "street1": "1901 W Madison Street",
    "city": "Chicago",
    "state": "IL",
    "postal_code": "60612",
    "country": "US",
    "street2": "Press Box 23",
    "name": "Michael Jordan",
    "company": "Only The Bulls",
    "phone": "123-345-5678",
    "email": "mj@onlythebulls.com"
  },
  "config": {
    "signature_required": false,
    "adult_signature_required": true,
    "hazmat": true,
    "perishable": false,
    "other_metadata": {}
  },
  "allowed_ship_methods": [
    "Better Trucks"
  ],
  "external_order_id": "ORDER12345",
  "external_shipment_id": "SHIPMENT001",
  "return_address": {
    "street1": "999 S Oyster Avenue",
    "city": "Bethpage",
    "state": "NY",
    "postal_code": "11714",
    "country": "US",
    "street2": "#111A",
    "name": "Andrew Haner",
    "company": "Medusa Distribution",
    "phone": "312-555-1212",
    "email": "andrew@medusadistribution.com"
  },
  "total_shipments_in_order": 1,
  "shipment_sequence_number": 1
}
```